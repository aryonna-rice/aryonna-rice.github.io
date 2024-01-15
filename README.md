# Aryonna Rice's Portfolio
## Table of Contents

1. [About Me](#about-me)
2. [What I Do Best](#what-i-do-best)
3. [Skills](#skills)
4. [Projects](#projects)
   1. [Saving Data to an MS SQL Database](#saving-data-to-an-ms-sql-database)
   2. [Website Application for Computer Science Clubs at UNC](#website-application-for-computer-science-clubs-at-unc)
   3. Dreamscape EEG Imaging
6. [Contact Information](#contact-information)

## About Me
Hi! I'm Aryonna, a passionate senior computer science student at the University of North Carolina at Chapel Hill with a flair for backend development. My expertise lies in crafting robust solutions using Python and Java. Proficient in SQL ORM, SQL CORE, and MS SQL, I delve into the intricacies of databases with ease. I am a problem solver and love a good challenge!

## What I Do Best
I thrive on problem-solving and enjoy the creative process of designing efficient solutions. Whether it's untangling complex coding challenges or engineering seamless backend systems, I'm in my element when transforming problems into elegant solutions.

## Skills
1. Python - Fluent
2. Java - Fluent
3. Lisp - Knowledgable
4. ML - Knowledgable
5. Prolog - Knowledgable
6. SQL – Knowledgeable
7. MS SQL – Knowledgeable
8. PostgreSQL – Knowledgeable
9. SQL ORM – Knowledgeable
10. Google Certified Associate Cloud Engineer
    
## Projects

## Saving Data to an MS SQL Database

### Task
Save data from a Pandas dataframe into a preexisting table in the company's MS SQL database in long and JSON format.

### Problem
Prior to my undertaking of the project, there was no interim table for data to be stored in one of the company's databases. The table my boss wanted me to create served as temporary storage for data (before it was saved to more specific tables). Overall, data from different dataframes would be saved in this table temporarily.

### Requirements / Criteria
- Remove all special characters and spaces from column names.
- Save data under new column names (col_name, col_val, data, etc).
- Dataframes with fewer than 1 million rows must all be inserted in under 60 seconds.

### Walk-through
The data to be inserted into the temporary table is originally held in a Pandas dataframe and looks something like <a href="https://github.com/aryonna-rice/aryonna-rice.github.io/blob/main/screenshots/Original.png" style="color:blue;">this</a>. The data would look like <a href="https://github.com/aryonna-rice/aryonna-rice.github.io/blob/main/screenshots/Long.png" style="color:blue;">this</a> in the long format table in the MS SQL database and would look like <a href="https://github.com/aryonna-rice/aryonna-rice.github.io/blob/main/screenshots/JSON.png" style="color:blue;">this</a> if saved in the JSON format table.

### Skills Learned
- Setting up a connection with a database
  - pyodbc
- Pandas:
  - to_sql, melt, pivot, merge, concat, etc
  - numpy
- SQL:
  - Writing raw queries: (SELECT and DELETE WHERE, etc)
  - Injection attack-proof queries
- Python code:
  - Created data-cleaning functions
  - Utilized regular expressions
    - re library
  - Utilized concurrency (ThreadPoolExecutor) to insert data in batches

### Results
#### Long Format
- Saved ~840,000 rows of data in 53.87 seconds.

#### JSON Format
- Saved ~11,800 rows of data in 12.34 seconds.

### Additional Achievements
- Team adopted my code into production.
- Offered a full-time position post-grad.

## Website Application for Computer Science Clubs at UNC

### Course
Web Development - COMP590

### Project Description
Design a website for Computer Science clubs at UNC for their use.

### My Role
- Worked on implementing APIs for seamless data communication using FastAPI.
- Utilized PostgreSQL for database management and integration.
- Developed application logic to ensure a smooth user experience.

### Results
- Promoted to tech lead based on the volume and quality of code produced.
- Received an A on the final project.
- Built strong connections with group members.

### Visuals

#### ![Web application club view](https://github.com/comp423-23s/final-project-final-c3/blob/stage/docs/images/filtering_view.png)
This image shows what a user sees when they click all clubs. 

#### Tables I Created
<table>
  <tr>
   <td>
Name
   </td>
   <td>Description
   </td>
   <td>Attributes
   </td>
  </tr>
  <tr>
   <td><a href="https://github.com/comp423-23s/final-project-final-c3/blob/stage/backend/entities/club_entity.py" style="color:blue;">Club Entity</a></td>
   <td>There are many organizations that might be a part of the UNC XL. Each one needs to have the following information: an id (int), a club_code (int) used by leaders of the club, a name(str), a description (str) for users, a list of members (List[UserEntity]), and a list of leaders (List[UserEntity])
   </td>
   <td>id, club_code, name, description, members, leaders
   </td>
  </tr>
  <tr>
   <td><a href="https://github.com/comp423-23s/final-project-final-c3/blob/stage/backend/entities/event_entity.py" style="color:blue;">Event Entity</a></td>
   <td>Each event hosted by a club has its own entity. It has an id (int), a name (str), a description of the event (str), a location for the event (str), the date that it occurs (datetime), a club_id to match the event to the corresponding club (int), and a list of attendees (List[UserEntity])
   </td>
   <td>id, name, location, description, date, club_id, attendees
   </td>
  </tr>
  <tr>
   <td><a href="https://github.com/comp423-23s/final-project-final-c3/blob/stage/backend/entities/potential_club_entity.py" style="color:blue;">Potential Club Entity</a></td>
   <td>Before a club can be declared an official club entity, it must be approved by an administrator. Thus, it remains as a ‘potential club entity’ until it is approved. These entities are composed of an id (int), a name (str), a description (str), and a founder_id (UserEntity) to represent who started the club. 
   </td>
   <td>id, name, description, founder_id
   </td>
  </tr>
  <tr>
   <td><a href="https://github.com/comp423-23s/final-project-final-c3/blob/stage/backend/entities/role_entity.py" style="color:blue;">Role Entity</a></td>
   <td>Each user of this application has a role. They may be a student, a leader (of a club), or an administrator. The attributes are: id (int), name (str), users (List[UserEntity]), permissions (List[PermissionEntity]0
   </td>
   <td>id, name, users, permissions
   </td>
  </tr>
  <tr>
   <td><a href="https://github.com/comp423-23s/final-project-final-c3/blob/stage/backend/entities/user_entity.py" style="color:blue;">User Entity</a></td>
   <td>Each user of this application has information that needs to be stored so that they can access different parts of the site. When signing in, one needs to fill out a ‘Profile’ form with the following information: First Name (str), Last Name (str), UNC email (str), and Pronouns (str). Then, each user has specific roles (List[RoleEntity]), permissions they are allowed (List[PermissionEntity]), clubs they are a part of (List[ClubEntity]), and clubs they are a leader of (List[ClubEntity]).
   </td>
   <td>id, pid, onyen, email, first_name, last_name, pronouns, roles, permissions, clubs, leading_clubs
   </td>
  </tr>
    <td><a href="https://github.com/comp423-23s/final-project-final-c3/blob/stage/backend/entities/category_entity.py" style="color:blue;">Category Entity</a></td>
   <td> Upon creation, each club has the option to be associated with certain tags or attributes. This makes the club able to be searched by a student when they search through clubs by filtering through them. The possible categories to choose from are: Black/African American, Asian American/Pacific Islander, Volunteer, Women, Hispanic/Latinx, LGBTQIA+, Video Games, Hackathon, Non-Binary, Volunteer, iOS Development, Business, and Project Management. The Category Entity has a list of clubs and Potential Clubs that have a specific Category ID. This information is stored in two different secondary tables, one for potential clubs and one for real clubs.
   </td>
   <td>id: Mapped[int] , name: Mapped[str], clubs: Mapped[list[ClubEntity]], potential_clubs: Mapped[list[PotentialClubEntity]]
   </td>
  </tr>
  <tr>
  <td><a href="https://github.com/comp423-23s/final-project-final-c3/blob/stage/backend/entities/week_day_time_entity.py" style="color:blue;">WeekDayTime Entity</a></td>
   <td> A WeekDayTime Entity is keeps track of the weekday (Monday, Tuesday, etc) and the time (4:00PM, 9:30 AM, ect) that a club meets. This entity was created because a standard datetime object wasn't applicable. The start and end times of an event are converted to strings in the from model method to work around issues with backend and front end time objects. Each WeekDayTime entity is associated with one singular Potential Club Entity or Club Entity.
   </td>
   <td>id: Mapped[int], day: Mapped[str], start_time: Mapped[time], end_time: Mapped[time]
   </td>
  </tr>
  <tr>
</table>

#### Club Filtering - Most Notable Feature
The ability for a user to filter all clubs based on personal interests and availability was a feature I proposed the team implement. The idea behind this was to give users the ability to quickly search for clubs they are interested in. Below is the code snippet of how I implemented this feature and <a href="https://github.com/comp423-23s/final-project-final-c3/blob/stage/docs/images/filtering_view.png" style="color:blue;">this</a> is what filtering looked like for the user. 

```python
def filter_by_availability(self, availabilities: list[Tuple[str, str]]) -> list[int]:
    """Returns a list of clubs that meet at the times specified by the student."""
    final_club_ids: list[int] = []
    week_day_time_ids: list[int] = []
    morning_start: time = time(hour=6, minute=0)
    morning_end: time = time(hour=12, minute=0)
    afternoon_end: time = time(hour=17, minute=0)
    evening_end: time = time(hour=23, minute=59)
    for availability in availabilities:
        if availability[1] == "Morning":
            query = select(WeekDayTimeEntity).where(
                WeekDayTimeEntity.start_time >= morning_start,
                WeekDayTimeEntity.start_time < morning_end,
                WeekDayTimeEntity.day == availability[0]
            )
        elif availability[1] == "Afternoon":
            query = select(WeekDayTimeEntity).where(
                WeekDayTimeEntity.start_time >= morning_end,
                WeekDayTimeEntity.start_time < afternoon_end,
                WeekDayTimeEntity.day == availability[0]
            )
        elif availability[1] == "Evening":
            query = select(WeekDayTimeEntity).where(
                WeekDayTimeEntity.start_time >= afternoon_end,
                WeekDayTimeEntity.start_time < evening_end,
                WeekDayTimeEntity.day == availability[0]
            )
        week_day_time_entities = self._session.scalars(query).all()
        for week_day_time in week_day_time_entities:
            week_day_time_ids.append(week_day_time.id)
    # Select club_id based on WDT id
    for week_day_time_id in week_day_time_ids:
        query1 = select(WeekDayTimeEntity.club_id).where(WeekDayTimeEntity.id == week_day_time_id)
        club_ids = self._session.scalars(query1).all()
        for club_id in club_ids:
            final_club_ids.append(club_id)
    return final_club_ids

def filter_by_category(self, categories: list[str]) -> list[int]:
    """Returns a list of clubs based on a student's preferred categories."""
    final_club_ids: list[int] = []
    all_categories_ids: list[int] = []
    for category in categories:
        query = select(CategoryEntity.id).where(CategoryEntity.name == category)
        category_id = self._session.scalar(query)
        all_categories_ids.append(category_id)
    for category_id in all_categories_ids:
        query2 = select(club_category_table.c.club_id).where(club_category_table.c.category_id == category_id)
        club_ids = self._session.scalars(query2).all()
        for club_id in club_ids:
            final_club_ids.append(club_id)
    return final_club_ids

def filter_by_availability_and_category(self, availabilities: list[Tuple[str, str]], categories: list[str]) -> list[Club]:
    """Filters by availability and category."""
    set_club_ids = set()
    clubs: list[Club] = []
    filtered_by_availability: list[int] = self.filter_by_availability(availabilities)
    filtered_by_categories: list[int] = self.filter_by_category(categories)
    for club_id_by_availability in filtered_by_availability:
        set_club_ids.add(club_id_by_availability)
    for club_id_by_category in filtered_by_categories:
        set_club_ids.add(club_id_by_category)
    for an_id in set_club_ids:
        club_entity = self._session.get(ClubEntity, an_id)
        clubs.append(club_entity.to_model())
    return clubs
```

#### FastAPI Use
Below is a code snippet of one of the ways I used FastAPI to fulfill HTTP requests for our application. 

```python
@api.post("/filter", response_model=list[Club], tags=['Club'])
def filter(
    body: list[list],
    club_svc: ClubService = Depends()
):
    """Gets all clubs according to specified availability and categories."""
    try:
        return club_svc.filter_by_availability_and_category(availabilities=body[0], categories=body[1])
    except Exception as e:
        raise HTTPException(status_code=404, detail=str(e))
```

#### Potential Club to Club
As described above, once a user submits a proposal to create a club, that club is not a real club until the request gets approved, thus introducing the need for a separate table. Below is the logic of making a potential club a real club. 

```python
def create_club(self, potential_club: PotentialClub) -> None:
        """Approves the potential club request and adds it to the club table."""
        user_entity = self._session.get(UserEntity, potential_club.founder_id)
        user_entity.add_role(role=self._session.get(RoleEntity, 2))
        club_code = generate_random_club_code()
        new_club: Club = Club(club_code= club_code, name=potential_club.name, description=potential_club.description)
        club_entity = ClubEntity.from_model(new_club)
        self._session.add(club_entity)
        club_entity.members.append(user_entity)
        club_entity.leaders.append(user_entity)
        set_club_categories(potential_club, club_entity)
        potential_club_entity = self._session.get(PotentialClubEntity, potential_club.id)
        set_club_meetings_times(potential_club_entity, club_entity)
        stmt = delete(WeekDayTimeEntity).where(WeekDayTimeEntity.potential_club_id == potential_club.id)
        delete_and_commit(potential_club_entity)
```

#### Link to project's repository: (https://github.com/comp423-23s/final-project-final-c3)
Please navigate to the backend folder to view any work I contributed to. 

## Dreamscape EEG Imaging

## Project Description
"Dreamscape" was a collaborative project focused on transforming EEG brainwaves into images using the DreamDiffusion framework, which utilizes stable diffusion. The primary goal was to record brainwaves using the Muse SDK headset, process the data to generate images, store the data for research purposes, and display the generated images to users. My specific role in the project involved integrating the preexisting DreamDiffusion framework into our workflow.

## Skills Learned and Used
- Python programming
- Machine learning with PyTorch
- GPU utilization for model training
- SLURM script creation and usage
- Working with virtual machines (VMs), specifically Longleaf offered by UNC
- Manipulating Google Cloud Platform (GCP) buckets
- Setting up data storage and project structure on GCP
- SSH into VMs and using VSCode with VMs

## Achievements
- Learned and applied machine learning concepts without prior experience in the field.
- Established a data pipeline to record brainwaves, create images, and store data on GCP for research purposes.
- Practiced using GPUs for faster model training.
- Set up project infrastructure on GCP, including managing CSV files in GCP buckets.

## Generating Images Script
```python
PATIENT_IMAGE_BUCKET = "patient-eeg-images"
MODEL_PATH = "gs://eeg-checkpoint-files/pretrains-generation-checkpoint.pth"
ROOT = "../dreamdiffusion/"

def get_local_file_path(gcs_path: str) -> str:
    _, bucket_name, object_name = gcs_path.split('/', 2)
    local_temp_file = tempfile.NamedTemporaryFile(delete=False)
    local_temp_file_path = local_temp_file.name
    client = storage.Client()
    bucket = client.bucket(bucket_name)
    blob = bucket.blob(object_name)
    blob.download_to_filename(local_temp_file_path)
    return local_temp_file_path

def delete_local_path(local_path: str) -> None:
    os.remove(local_path)

 
def generate_image(patient_id: int, eeg_signals_path: str):
    """Creates 10 images based on the signals found at the eeg_signals_path."""
    # Define the GCS path based on patient_id and datetime
    datetime_str = datetime.datetime.now().strftime("%d-%m-%Y-%H-%M-%S")
    gcs_output_path = f"{PATIENT_IMAGE_BUCKET}/{patient_id}/{datetime_str}/"

    # Load pre-trained model checkpoint
    local_model_path = get_local_file_path(MODEL_PATH)
    sd = torch.load(local_model_path, map_location='cpu')
    config = sd['config']

    # update paths
    config.root_path = ROOT
    local_eeg_signals_path = get_local_file_path(eeg_signals_path)
    config.eeg_signals_path = local_eeg_signals_path
    local_pretrain_mbm_path = get_local_file_path("gs://eeg-checkpoint-files/results-eeg_pretrain-28-11-2023-21-07-25-checkpoints-checkpoint.pth")
    config.pretrain_mbm_path = local_pretrain_mbm_path
    config.pretrain_gm_path = 'pretrains/'

    print("Updated config:")
    print(config.__dict__)
    
    print(f"Generated output path: {gcs_output_path}")
    device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')

    img_transform_test = transforms.Compose([
        normalize, transforms.Resize((512, 512)), 
        channel_last
    ])
    
    dataset_test = EEGDataset(config.eeg_signals_path, img_transform_test, subject=4)
    num_voxels = dataset_test.dataset.data_len
    print(len(dataset_test))

    # prepare pretrained mae 
    pretrain_mbm_metafile = torch.load(config.pretrain_mbm_path, map_location='cpu')

# Initialize Generative Model
    generative_model = eLDM(pretrain_mbm_metafile, num_voxels,
                            device=device, pretrain_root=config.pretrain_gm_path,
                            ddim_steps=config.ddim_steps, global_pool=config.global_pool,
                            use_time_cond=config.use_time_cond)
    generative_model.model.load_state_dict(sd['model_state_dict'], strict=False)
    print('Loaded generative model successfully')
    state = sd['state']

    # Generate Samples using new, unseen EEG data
    grid, samples = generative_model.generate(dataset_test, config.num_samples,
                                            config.ddim_steps, config.HW, limit=None, state=state,
                                            output_path=gcs_output_path)

        # Iterate through each sample and save it individually
    for i, sample in enumerate(samples):
        # Convert the sample to an image
        img = Image.fromarray((255. * sample.cpu().numpy()).astype(np.uint8))

        # Create a temporary local file to save the image
        local_image_file = tempfile.NamedTemporaryFile(delete=False, suffix=".png")
        local_image_file_path = local_image_file.name

        # Save the individual image
        img.save(local_image_file_path)

        # Upload the local image file to GCS
        client = storage.Client()
        blob_name = f"sample_{i}.png"  # Adjust the blob name as needed
        blob = client.bucket(PATIENT_IMAGE_BUCKET).blob(f"{patient_id}/{datetime_str}/{blob_name}")
        blob.upload_from_filename(local_image_file_path)
        # Delete the local image file
        delete_local_path(local_image_file_path)

    delete_local_path(local_image_file_path)
    delete_local_path(local_eeg_signals_path)
    delete_local_path(local_pretrain_mbm_path)
    delete_local_path(local_model_path)
```


## Project Repositories
- [Dreamscape Team Repository](https://github.com/aryonna-rice/comp-523-dreamscape)
- [DreamDiffusion Framework Repository](https://github.com/bbaaii/DreamDiffusion)

This project was a valuable learning experience, pushing my boundaries in machine learning and cloud computing.




## Contact Information
- Email: aryonnarice@unc.edu
- LinkedIn: https://www.linkedin.com/in/aryonna-rice/


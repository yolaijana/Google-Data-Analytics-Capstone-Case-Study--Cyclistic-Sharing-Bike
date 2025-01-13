# Google-Data-Analytics-Capstone-Case-Study--Cyclistic-Sharing-Bike
Google Data Analytics Capstone. Analyzed Cyclistic bike-sharing data to identify trends &amp; actionable insights. Involved data cleaning, EDA, visualization, &amp; developing recommendations. Demonstrates skills in data manipulation, analysis, &amp; visualization learned during the program.




## Google Data Analytics Capstone: Case Study- Cyclistic, Sharing Bike
### Introduction

The case study on “Cyclistic, sharing bike” a fictional bikeshare firm located in Chicago. The company owns and operates over 5000 bicycles that are distributed and locked into a network of over 600 stations across Chicago. The company serves two types of customers, who purchase single-ride passes or full-day passes (The casual riders), and who purchase annual memberships (The annual members). The marketing director was interested in maximizing the number of annual members by creating marketing strategies that aid in the conversion of more casual riders to annual members, because they found that the annual members are much more profitable than casual riders. My responsibility was to make data-driven recommendations for the marketing campaign by highlighting the differ between the way that the two types of customers behave.


### Statement of the Business Task

To highlight the difference between the annual members and casual riders while using the Cyclistic sharing bikes.


### The Dataset
I used the “Divvy Bikeshare Dataset,” which is owned by the “Divvy” bike sharing company. The data is a third-party dataset made public by Motivate International Inc., the firm that runs the Divvy bike-sharing service.
The link to the dataset: https://divvy-tripdata.s3.amazonaws.com/index.html
Data is available from the Apr 2020 till Nov 2024. The dataset is structured in the form of spreadsheet.
Issues with the dataset: There is missing value in the data and some of the column names are inconsistent.


### Installing and Loading Packages
I used various packages in R Studio, such as, Tidyverse, Lubridate (for datetime functions), Tidyr (for data-cleaning), ggplot2 (for creating visualizations) and many others.

```{r Install & load packages}
install.packages("tidyverse")
library(tidyverse)
library(readr)
library(dplyr)
library(tidyr)
library(lubridate)
library(ggplot2)
```

Getting my Data Ready in R Studio.
After downloading the all data files I start importing them by using the read_csv() function from the readr package.

```{r Importing data}
apr_data_2020 <- read_csv("C:/Users/yolai/Downloads/202004-divvy-tripdata.csv")
may_data_2020 <- read_csv("C:/Users/yolai/Downloads/202005-divvy-tripdata.csv")
jun_data_2020 <- read_csv("C:/Users/yolai/Downloads/202006-divvy-tripdata.csv")
jul_data_2020 <- read_csv("C:/Users/yolai/Downloads/202007-divvy-tripdata.csv")
aug_data_2020 <- read_csv("C:/Users/yolai/Downloads/202008-divvy-tripdata.csv")
sep_data_2020 <- read_csv("C:/Users/yolai/Downloads/202009-divvy-tripdata.csv")
oct_data_2020 <- read_csv("C:/Users/yolai/Downloads/202010-divvy-tripdata.csv")
nov_data_2020 <- read_csv("C:/Users/yolai/Downloads/202011-divvy-tripdata.csv")
dec_data_2020 <- read_csv("C:/Users/yolai/Downloads/202012-divvy-tripdata.csv")

jan_data_2021 <- read_csv("C:/Users/yolai/Downloads/202101-divvy-tripdata.csv")
feb_data_2021 <- read_csv("C:/Users/yolai/Downloads/202102-divvy-tripdata.csv")
mar_data_2021 <- read_csv("C:/Users/yolai/Downloads/202103-divvy-tripdata.csv")
apr_data_2021 <- read_csv("C:/Users/yolai/Downloads/202104-divvy-tripdata.csv")
may_data_2021 <- read_csv("C:/Users/yolai/Downloads/202105-divvy-tripdata.csv")
jun_data_2021 <- read_csv("C:/Users/yolai/Downloads/202106-divvy-tripdata.csv")
jul_data_2021 <- read_csv("C:/Users/yolai/Downloads/202107-divvy-tripdata.csv")
aug_data_2021 <- read_csv("C:/Users/yolai/Downloads/202108-divvy-tripdata.csv")
sep_data_2021 <- read_csv("C:/Users/yolai/Downloads/202109-divvy-tripdata.csv")
oct_data_2021 <- read_csv("C:/Users/yolai/Downloads/202110-divvy-tripdata.csv")
nov_data_2021 <- read_csv("C:/Users/yolai/Downloads/202111-divvy-tripdata.csv")
dec_data_2021 <- read_csv("C:/Users/yolai/Downloads/202112-divvy-tripdata.csv")

jan_data_2022 <- read_csv("C:/Users/yolai/Downloads/202201-divvy-tripdata.csv")
feb_data_2022 <- read_csv("C:/Users/yolai/Downloads/202202-divvy-tripdata.csv")
mar_data_2022 <- read_csv("C:/Users/yolai/Downloads/202203-divvy-tripdata.csv")
apr_data_2022 <- read_csv("C:/Users/yolai/Downloads/202204-divvy-tripdata.csv")
may_data_2022 <- read_csv("C:/Users/yolai/Downloads/202205-divvy-tripdata.csv")
jun_data_2022 <- read_csv("C:/Users/yolai/Downloads/202206-divvy-tripdata.csv")
jul_data_2022 <- read_csv("C:/Users/yolai/Downloads/202207-divvy-tripdata.csv")
aug_data_2022 <- read_csv("C:/Users/yolai/Downloads/202208-divvy-tripdata.csv")
sep_data_2022 <- read_csv("C:/Users/yolai/Downloads/202209-divvy-tripdata.csv")
oct_data_2022 <- read_csv("C:/Users/yolai/Downloads/202210-divvy-tripdata.csv")
nov_data_2022 <- read_csv("C:/Users/yolai/Downloads/202211-divvy-tripdata.csv")
dec_data_2022 <- read_csv("C:/Users/yolai/Downloads/202212-divvy-tripdata.csv")

jan_data_2023 <- read_csv("C:/Users/yolai/Downloads/202301-divvy-tripdata.csv")
feb_data_2023 <- read_csv("C:/Users/yolai/Downloads/202302-divvy-tripdata.csv")
mar_data_2023 <- read_csv("C:/Users/yolai/Downloads/202303-divvy-tripdata.csv")
apr_data_2023 <- read_csv("C:/Users/yolai/Downloads/202304-divvy-tripdata.csv")
may_data_2023 <- read_csv("C:/Users/yolai/Downloads/202305-divvy-tripdata.csv")
jun_data_2023 <- read_csv("C:/Users/yolai/Downloads/202306-divvy-tripdata.csv")
jul_data_2023 <- read_csv("C:/Users/yolai/Downloads/202307-divvy-tripdata.csv")
aug_data_2023 <- read_csv("C:/Users/yolai/Downloads/202308-divvy-tripdata.csv")
sep_data_2023 <- read_csv("C:/Users/yolai/Downloads/202309-divvy-tripdata.csv")
oct_data_2023 <- read_csv("C:/Users/yolai/Downloads/202310-divvy-tripdata.csv")
nov_data_2023 <- read_csv("C:/Users/yolai/Downloads/202311-divvy-tripdata.csv")
dec_data_2023 <- read_csv("C:/Users/yolai/Downloads/202312-divvy-tripdata.csv")

jan_data_2024 <- read_csv("C:/Users/yolai/Downloads/202401-divvy-tripdata.csv")
feb_data_2024 <- read_csv("C:/Users/yolai/Downloads/202402-divvy-tripdata.csv")
mar_data_2024 <- read_csv("C:/Users/yolai/Downloads/202403-divvy-tripdata.csv")
apr_data_2024 <- read_csv("C:/Users/yolai/Downloads/202404-divvy-tripdata.csv")
may_data_2024 <- read_csv("C:/Users/yolai/Downloads/202405-divvy-tripdata.csv")
jun_data_2024 <- read_csv("C:/Users/yolai/Downloads/202406-divvy-tripdata.csv")
jul_data_2024 <- read_csv("C:/Users/yolai/Downloads/202407-divvy-tripdata.csv")
aug_data_2024 <- read_csv("C:/Users/yolai/Downloads/202408-divvy-tripdata.csv")
sep_data_2024 <- read_csv("C:/Users/yolai/Downloads/202409-divvy-tripdata.csv")
oct_data_2024 <- read_csv("C:/Users/yolai/Downloads/202410-divvy-tripdata.csv")
nov_data_2024 <- read_csv("C:/Users/yolai/Downloads/202411-divvy-tripdata.csv")
```

### Data Exploration to Assuring the Datatypes Consistency

I checked the files one by one using the str() function to verify if there is un consistency in the dataset, So I found that the columns start_station_id and end_station_id are double datatype in the datasets starting from Apr 2020 - Nov 2020 while these fields are character datatype in the rest of data from Dec 2020 - Nov 2024.

```{r Explore data}
str(apr_data_2020) 
```
I repeated for all the data files.


#### Solve Tha Data Consistency Issue

To ensure datatype consistency in the datasets, I converted the columns start_station_id and  end_station_id to character datatype for the data files from Apr 2020 - Nov 2020 so now the two fields are character datatype in all the datasets.

```{r Managing datatype }
apr_data_2020 <- apr_data_2020 %>%
mutate(start_station_id=as.character(start_station_id),end_station_id=as.character(end_station_id))

may_data_2020 <- may_data_2020 %>%
mutate(start_station_id=as.character(start_station_id),end_station_id=as.character(end_station_id))

jun_data_2020 <- jun_data_2020 %>%
mutate(start_station_id=as.character(start_station_id),end_station_id=as.character(end_station_id))

jul_data_2020 <- jul_data_2020 %>%
mutate(start_station_id=as.character(start_station_id),end_station_id=as.character(end_station_id))

aug_data_2020 <- aug_data_2020 %>%
mutate(start_station_id=as.character(start_station_id),end_station_id=as.character(end_station_id))

sep_data_2020 <- sep_data_2020 %>%
mutate(start_station_id=as.character(start_station_id),end_station_id=as.character(end_station_id))

oct_data_2020 <- oct_data_2020 %>%
mutate(start_station_id=as.character(start_station_id),end_station_id=as.character(end_station_id))

nov_data_2020 <- nov_data_2020 %>%
 mutate(start_station_id=as.character(start_station_id),end_station_id=as.character(end_station_id))
```

### Combining the Data
I combined all the data files in one dataset “data_combined” using the rbind () function 

```{r combine data}
data_combined <- rbind(
  apr_data_2020, may_data_2020, jun_data_2020, jul_data_2020, aug_data_2020, sep_data_2020, oct_data_2020, nov_data_2020, dec_data_2020, jan_data_2021, feb_data_2021, mar_data_2021, apr_data_2021, may_data_2021, jun_data_2021, jul_data_2021, aug_data_2021, sep_data_2021, oct_data_2021, nov_data_2021, dec_data_2021, jan_data_2022, feb_data_2022, mar_data_2022, apr_data_2022, may_data_2022, jun_data_2022, jul_data_2022, aug_data_2022, sep_data_2022, oct_data_2022, nov_data_2022, dec_data_2022, jan_data_2023, feb_data_2023, mar_data_2023, apr_data_2023, may_data_2023, jun_data_2023, jul_data_2023, aug_data_2023, sep_data_2023, oct_data_2023, nov_data_2023, dec_data_2023, jan_data_2024, feb_data_2024, mar_data_2024, apr_data_2024, may_data_2024, jun_data_2024, jul_data_2024, aug_data_2024, sep_data_2024, oct_data_2024, nov_data_2024
)
str(data_combined)
```

### Data Cleaning
#### Removing null values

I used **drop_na()** function to remove the null values from the dataset. 
```{r Drob null values}
no_null_data <- drop_na(data_combined)         
str(no_null_data)
```

#### Check the Data Strucure after Drob the Null Values
```{r change the data name}
clean_data <- no_null_data
str(clean_data)
```

#### Exploring some the Data
```{r Check the data}
head(clean_data)
```


#### Remove the unnecessary fields
I removed the latitude and longitude fields from the data

```{r Remove fields}
clean_data <- clean_data %>%
  select(-c(start_lat, start_lng, end_lat, end_lng))
```

#### Explore the Data columns

I Explored the columns after removing the unnecessary ones

```{r Check columns}
colnames(clean_data)
```

#### Adding new columns

I added 3 columns to the dataset by abstracting the **date** and **month** from the column started_at, then I calculated new field for **ride_length** from the started_at and ended_at fields.

##### Create the date, month and ride_length columns

I Abstracted the date and month columns from the **started_at** column

```{r Create date & month field}
clean_data$date <- as.Date(clean_data$started_at)
clean_data$month <- format(as.Date(clean_data$date), "%B")
```


I created the **ride_length** by calculating the different time between the **ended_at** and **started_at** columns

```{r Calculate new field for ride_length}
clean_data <-clean_data %>%
  mutate (ride_length=difftime(ended_at, started_at, unit="mins"))
```

Again I checked the Data after adding the new fields using the **glimpse()** function

```{r Check the data}
glimpse(clean_data)
```


Verifying that the field ride_length containing only correct values

```{r Verifying the field ride_length contain correct values}
clean_data <- clean_data[!(clean_data$ride_length <= 0 | clean_data$ride_length > 1440),]
```

Change the data frame name to final_data

```{r Rename the data frame}
final_data <- clean_data
```


### Analysis

Here I will analyse the data to find some patterns and trends in it, so I start by calculating the **mean, median, max and min** for all the dataset to exploring the data.

```{r Anal. step1}
final_data %>%
  summarise(ride_length_mean=mean(ride_length)
            ,ride_length_median=median(ride_length)
            ,ride_length_min=min(ride_length)
            ,ride_length_max=max(ride_length))
```

A tibble: 1 × 4
  ride_length_mean ride_length_median ride_length_min  ride_length_max
  <drtn>           <drtn>             <drtn>           <drtn>         
1 18.52197 mins    11.21667 mins      0.001716669 mins 1439.9 mins  





#### Calculate the mean, median, max and min by the rider type

I calculated the mean for ride length grouping by the rider type

```{r # Calculate the mean by rider type}
mean_by_rider_type <- final_data %>%
  group_by(member_casual) %>%
  summarize(mean_ride_length = mean(ride_length, na.rm = TRUE))
mean_by_rider_type
```

 A tibble: 2 × 2
  member_casual mean_ride_length
  <chr>         <drtn>          
1 casual        26.8789 mins    
2 member        13.0062 mins   


I calculated the median for ride length grouping by the rider type

```{r # Calculate the median by rider type}
median_by_rider_type <- final_data %>%
  group_by(member_casual) %>%
  summarize(median_ride_length = median(ride_length, na.rm = TRUE))
median_by_rider_type
```

A tibble: 2 × 2
  member_casual median_ride_length
  <chr>         <drtn>            
1 casual        15.266667 mins    
2 member         9.366667 mins  



I calculated the max for ride length grouping by the rider type

```{r # Calculate the max by rider type}
max_by_rider_type <- final_data %>%
  group_by(member_casual) %>%
  summarize(max_ride_length = max(ride_length, na.rm = TRUE))
max_by_rider_type
```

 A tibble: 2 × 2
  member_casual max_ride_length
  <chr>         <drtn>         
1 casual        1439.900 mins  
2 member        1439.867 mins


I calculated the min for ride length grouping by the rider type

```{r # Calculate the min by rider type}
min_by_rider_type <- final_data %>%
  group_by(member_casual) %>%
  summarize(min_ride_length = min(ride_length, na.rm = TRUE))
min_by_rider_type
```

A tibble: 2 × 2
  member_casual min_ride_length 
  <chr>         <drtn>          
1 casual        0.001716669 mins
2 member        0.002316666 mins



I counted the number of rides has taken by different types of customers (Annual member or Casual rider)

```{r Calculate the number of rides by the rider type}
num_rides_by_type <- final_data %>%
  group_by(member_casual) %>%
  summarize(num_rides = n_distinct(ride_id, na.rm = TRUE))
num_rides_by_type
```

 A tibble: 2 × 2
  member_casual num_rides
  <chr>             <int>
1 casual          8076615
2 member         12236918





Here I've calculated the most common stations that the casual riders are starting from every time the take a ride, I limited for the top 5 start stations

```{r Calculate the most common stations the casual riders starting from}
common_start_station <- final_data %>%
  filter(member_casual == "casual") %>%
  group_by(start_station_name) %>%       
  summarize(num_rides = n()) %>%         
  arrange(desc(num_rides)) %>%
  slice_head(n = 5)
common_start_station
```

  start_station_name                num_rider
  <chr>                                 <int>
1 Streeter Dr & Grand Ave              235034
2 Millennium Park                      113080
3 Michigan Ave & Oak St                109184
4 DuSable Lake Shore Dr & Monroe St    106403
5 Shedd Aquarium                        87137
                  


Here I've calculated the most common stations that the casual riders are ending their ride to, also I limited for the top 5 end stations

```{r Calculate the most common stations the casual riders ending to}
common_end_station <- final_data %>%
  filter(member_casual == "casual") %>%
  group_by(end_station_name) %>%       
  summarize(num_rides = n()) %>%         
  arrange(desc(num_rides)) %>%
  slice_head(n = 5)
common_end_station
```

end_station_name                  num_rider
  <chr>                                 <int>
1 Streeter Dr & Grand Ave              251551
2 Millennium Park                      121556
3 Michigan Ave & Oak St                115171
4 DuSable Lake Shore Dr & Monroe St     99192
5 Theater on the Lake                   90186


### Create the Visualizations

```{r Create pie chart, echo=FALSE}
# Add percentage column
num_rides_by_type <- num_rides_by_type %>%
  mutate(percentage = num_rides / sum(num_rides) * 100)

# Create Pie Chart for the Number of Rides: Annual Members vs Casual Riders
ggplot(num_rides_by_type, aes(x = "", y = num_rides, fill = member_casual)) +
  geom_bar(stat = "identity", width = 1) +
  coord_polar(theta = "y") +
  geom_text(aes(
    label = paste0(num_rides, " (", round(percentage, 1), "%)")
  ), position = position_stack(vjust = 0.5)) +
  labs(
    title = "Number of Rides: Annual Members vs Casual Riders",
    fill = "Rider Type"
  ) +
  theme_void()
```
  


#### Pie chart

This pie chart I created to explore the Number of Rides for the Annual Members vs Casual Riders



```{r Create Bar Chart1, echo=FALSE}
ggplot(common_start_station, aes(x =  reorder(start_station_name, -num_rides), y = num_rides, fill = "blue")) +
  geom_bar(stat = "identity") +
  labs(title = "Top 5 Common Start Stations",
       x = "Start Station Name", y = "Number of Rides") +
  scale_fill_manual(values = c("blue")) +
  scale_y_continuous(breaks = seq(0, max(common_start_station$num_rides), by = 25000)) + # Set y-axis breaks
  theme(axis.text.x = element_text(angle = 45, hjust = 1)) # Rotate x-axis labels for readability
```


```{r Create Bar Chart2, echo=FALSE}
ggplot(common_end_station, aes(x =  reorder(end_station_name, -num_rides), y = num_rides, fill = "red")) +
  geom_bar(stat = "identity") +
  labs(title = "Top 5 Common End Stations",
       x = "End Station Name", y = "Number of Rides") +
  scale_y_continuous(breaks = seq(0, max(common_end_station$num_rides), by = 25000)) + # Set y-axis breaks
  theme(axis.text.x = element_text(angle = 45, hjust = 1)) # Rotate x-axis labels for readability
```
    


#### Bar chart to explore the Top 5 common Stations the Casual Rider Start from

This pie chart I created to explore the Top 5 common Stations the Casual Rider are staring their rides from to use these stations for the marketing campaign later

#### Bar chart to explore the Top 5 common Stations the Casual Rider End to

This pie chart I created to explore the Top 5 common Stations the Casual Rider end their rides at to use them also for the marketing campaign, and I discovered that the top 4 stations the casual riders start from are the same top 4 stations end to.
 

#### Histogram chart to explore the number of rides taken by the casual riders per month

```{r Create bar chart3, echo=FALSE}
final_data %>%
  group_by(month, member_casual) %>%
  summarise(num_rides = n(), .groups = 'drop') %>%
  filter(member_casual == 'casual') %>%
  arrange(desc(num_rides)) %>%
  mutate(
    month = month(ymd(paste0("2021-", month, "-01")), label = TRUE, abbr = TRUE) 
  ) %>%
  ggplot(aes(x = month, y = num_rides)) +
  geom_col(fill = "blue", color = "black") +
  geom_text(aes(label = scales::comma(num_rides)), vjust = -0.5, size = 3) +
  labs(
    title = "Number of Rides Taken By Casual Riders",
    subtitle = "The number of rides taken by casual riders per month",
    x = "Month",
    y = "Number of Rides",
    caption = "Source: Ride Sharing Dataset"
  ) +
  scale_y_continuous(breaks = NULL) + 
  theme_minimal() +
  theme(
    plot.title = element_text(face = "bold", size = 16, hjust = 0.5),
    plot.subtitle = element_text(size = 12, hjust = 0.5),
    axis.title.x = element_text(size = 14, face = "bold", margin = margin(t = 10)),
    axis.title.y = element_text(size = 14, face = "bold", margin = margin(r = 10)),
    axis.text = element_text(size = 12),
    plot.caption = element_text(size = 10, hjust = 1, color = "gray")
  )
```

This Histogram chart exploring the number of rides has been taken by the casual riders per month to find the maximum number of rides its been taken in which months 

### My Recommondations

1. As we explore the data and visuals I recommend to use the top 4 stations **(Streeter Dr & Grand Ave, Millennium Park, Michigan Ave & Oak St, DuSable Lake Shore Dr & Monroe St)** in the marketing campaign by making Billboards, flyers and posters in these stations that convincing the casual riders to convert to annual members
2. It's clearly that the **Streeter Dr & Grand Ave** station is most common station and have very high number of casual rider are passing by in the beginning or ends their rides, so I recommend to make special offer for annual members who passing by it in their 1st year at least that will attract more casual riders. 
3. I see also it's helpful to Intensify the marketing campaign in the summer **(June, July, August and September)** because it's the most months that the casual riders are using the bike sharing services. 

# load packages
library(WDI)
library(ggplot2)

# update wdi cache of indicators
new_cache = WDIcache()


str(new_cache[[1]])
summary(new_cache[[1]])
head(new_cache[[1]])

str(new_cache[[2]])
summary(new_cache[[2]])
head(new_cache[[2]])


# convert to data frames
indicator_info <- as.data.frame(new_cache[[1]], stringsAsFactors = TRUE)
country_info <- as.data.frame(new_cache[[2]], stringsAsFactors = TRUE)

# search for data using keywords, displays only first 10 rows
?WDIsearch
WDIsearch('gdp')[1:10,]

# data for GDP per capita for mexico, canada, and us, from 1960 - 2012
gdp_data <- WDI(indicator='NY.GDP.PCAP.KD', country= c('MX','CA','US'), start=1960, end=2012)

# plot data


ggplot(gdp_data, aes(year, NY.GDP.PCAP.KD, color=country)) + 
  geom_line() + 
  xlab('Year') + 
  ylab('GDP per capita')


# Percentage of students enrolled in primary education who are over-age, both sexes (%)
# for mexico, canada, and us, for all possible years
overage_students <-WDI("UIS.OAEP.1", country = c("US","MX","CA"), cache = new_cache, extra = F)

#plot
ggplot(overage_students, aes(year, UIS.OAEP.1 , color=country)) + 
  geom_point() + 
  xlab('Year') + 
  ylab('% over age students')


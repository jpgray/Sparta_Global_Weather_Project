# Sparta_Global_Weather_Project

### Before using any service:

This project requires a number of gems to be installed, which are included in the gemfile for convenience. Please run 'bundle' and they will be installed for you.

You will also need an API key, which should not be shared online, and has therefore been hidden. You can get an API key by creating an account at 'https://openweathermap.org/api'.

Following this, please create a file named '.env' in the main project directory. This file should include your api key, in the format "OPENWEATHER_API_KEY=000000000", where 000000000 is replaced with your API key.

Then simply run 'rspec' to run the test.

## Current Day Service





## Five Day Service

This portion checks the results from calling the Open Weather API for a 5 day forecast, in three hour increments. It will provide a new, randomly generated set of coordinates to the API each time the test is run. These coordinates are generated in the coordinates_generator.rb file.

### The coordinates generator

This file is used in the test to generate random coordinates through a set of two methods: generate_latitude and generate_longitude, respectively. This generator is tested in turn through the coordinates_generator_spec file. Specifically, it must generate floats that are valid coordinates.

### The Service

The Five Day Weather Service has six methods to assist testing. These are designed to be reused in future tests.

The get_five_day_data method uses your API key and generated coordinates to make an http request to the API. It then returns the body of the response.

The body of the response will be an hash containing many different data types, resulting in a structure with many layers. The search_outer method takes one parameter, and looks through the base hash for a key matching the parameter.

The search_inside_city_for method works the same, but will instead look inside the city hash.

The search_list_for method is slightly different, as it takes two parameters. The list hash contains 40 datasets, so the first parameter must be an integer to choose which of these to look at. The second parameter is for the desired key.

The search_weather_for method works this same as list, but for the weather hash.

The search_list_input_for method drills down one level further into the list hash. It takes three arguments in the following order: integer, desired hash key, and the key to search for. It otherwise functions the same as above.


## Sixteen Day Service

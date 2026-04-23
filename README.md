# majorProject
# Calories Tracker

A comprehensive GUI application for tracking daily calorie intake with manual entry and AI-powered image analysis.

## Description

This Python application provides an intuitive interface for logging meals and monitoring calorie consumption. It features:

- **Manual Entry**: Select from a built-in food database with predefined calorie values
- **Image Analysis**: Upload food photos and use AI (Anthropic Claude) to estimate calories automatically
- **Data Storage**: MongoDB integration with CSV fallback for offline use
- **Goal Tracking**: Set and monitor daily calorie goals
- **Visual Analytics**: Interactive charts showing meal distribution and progress
- **Weekly Overview**: Track calorie intake over the past 7 days

## Features

### Manual Entry Mode
- Predefined food database with common Indian and international foods
- Meal type categorization (Breakfast, Lunch, Dinner, Snack, etc.)
- Quantity adjustment for accurate calorie calculation
- Real-time calorie updates

### Image Analysis Mode
- Upload food photos (JPG, PNG, WebP)
- AI-powered calorie estimation using Anthropic Claude Vision API
- Editable calorie values based on AI analysis
- Automatic food name detection

### Data Management
- MongoDB database storage (with automatic fallback to CSV)
- Daily meal logging with timestamps
- Edit and delete entries
- Persistent storage across sessions

### Analytics & Visualization
- Today's calorie summary with goal progress
- Pie chart showing calories by meal type
- Progress bar for daily goal achievement
- Weekly calorie trend chart
- Entry count tracking

## Requirements

- Python 3.x
- tkinter (usually included with Python)
- pandas
- matplotlib
- numpy
- pymongo (for MongoDB support)
- Anthropic API key (for image analysis feature)

Install dependencies using:
```
pip install pandas matplotlib numpy pymongo
```

## Setup

1. **MongoDB Setup** (Optional):
   - Install MongoDB locally or use a cloud service
   - Update `MONGO_URI` in the code if using a different connection string
   - The app will automatically fall back to CSV storage if MongoDB is unavailable

2. **Anthropic API Setup** (For Image Analysis):
   - Get an API key from [Anthropic](https://console.anthropic.com/)
   - Replace `"YOUR_ANTHROPIC_API_KEY"` in the code with your actual key

3. **Run the Application**:
   ```
   python calories_tracker.py
   ```

## Usage

### Adding Meals Manually
1. Select "Manual Entry" mode
2. Choose meal type from dropdown
3. Select food item from the database
4. Adjust quantity if needed
5. Click "ADD ENTRY"

### Adding Meals via Image
1. Select "Image Upload" mode
2. Choose meal type
3. Click "Choose Food Photo" and select an image
4. Click "Analyse Image" to get AI calorie estimate
5. Edit the detected calories if needed
6. Click "ADD TO LOG"

### Setting Goals
- Enter your daily calorie goal in the "DAILY GOAL" section
- Click "Set" to update

### Viewing Analytics
- **Today's Log**: View all entries for the current day
- **Charts**: See meal distribution and goal progress
- **Weekly**: Track your intake over the past 7 days

## Data Storage

The application supports two storage modes:

### MongoDB (Preferred)
- Requires local MongoDB installation or cloud service
- Stores data in `calories_tracker` database, `meals` collection
- Persistent across sessions and devices

### CSV Fallback
- Automatic fallback when MongoDB is unavailable
- Stores data in `meal_log.csv` in the same directory
- Simple file-based storage for single-user scenarios

## Food Database

The app includes a built-in database of common foods with approximate calorie values:
- Fruits: Apple (95 kcal), Banana (105 kcal), etc.
- Indian foods: Roti (120 kcal), Dal (180 kcal), Paneer (265 kcal), etc.
- Proteins: Chicken Breast (165 kcal), Egg (78 kcal), etc.
- Beverages: Milk (149 kcal), Coffee (5 kcal), etc.

## Troubleshooting

### MongoDB Connection Issues
- Ensure MongoDB is running locally (default port 27017)
- Check `MONGO_URI` configuration
- App will automatically use CSV storage if MongoDB fails

### Image Analysis Not Working
- Verify Anthropic API key is correctly set
- Check internet connection
- Supported image formats: JPG, JPEG, PNG, WebP

### GUI Issues
- Ensure tkinter is installed (usually included with Python)
- Try running with `python -m tkinter` to test GUI support

## License

This project is open source. Feel free to modify and distribute.

## Customization

- Change `optimal_k = 3` to set a different number of clusters
- Modify `K_range = range(1, 11)` to test a different range of clusters
- Adjust `max_iter` and `n_init` parameters for KMeans fitting

## Troubleshooting

- Ensure your dataset file (`dataset.csv` or `dataset.xlsx`) is in the same directory as the script.
- Make sure all required packages are installed.
- If visualization doesn't appear, check your matplotlib backend settings.

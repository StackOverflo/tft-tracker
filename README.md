# TFT Game State Tracker

## Project Overview
A Python-based application that captures and analyzes Teamfight Tactics gameplay to track unit information and game state. The initial version focuses on tracking the player's own board and unit pool information.

## Core Components

### 1. Screen Capture System
- **Primary Technology**: `mss` library for efficient screen capture
- **Capture Strategy**:
  - Full-screen capture at regular intervals (configurable, default: 1 second)
  - Region of Interest (ROI) definitions:
    - Player board area
    - Unit shop
    - Unit pool information display
  - Capture resolution and quality settings
  - Frame buffering for performance optimization

### 2. Unit Recognition System
- **Primary Technology**: OpenCV for image processing
- **Components**:
  - Template matching system
    - Pre-stored unit templates
    - Multi-scale template matching
    - Confidence thresholding
  - Unit level detection (1-star, 2-star, 3-star)
    - Color analysis for star indicators
    - Size comparison for unit levels
  - Unit position tracking
    - Board grid mapping
    - Position persistence between frames

### 3. Overlay Display System
- **Primary Technology**: PyQt5 for overlay window
- **Display Components**:
  - Unit information panel
    - Current board composition
    - Unit levels and positions
  - Unit pool tracker
    - Available units by cost
    - Remaining unit counts
  - Basic statistics
    - Current trait counts
    - Unit synergies

## Development Phases

### Phase 1: Basic Setup
1. **Project Structure**
   ```
   tft_tracker/
   ├── src/
   │   ├── capture/
   │   │   ├── screen_capture.py
   │   │   └── regions.py
   │   ├── recognition/
   │   │   ├── unit_recognition.py
   │   │   └── templates/
   │   ├── overlay/
   │   │   ├── main_window.py
   │   │   └── components/
   │   └── utils/
   │       ├── config.py
   │       └── helpers.py
   ├── tests/
   ├── resources/
   └── requirements.txt
   ```

2. **Initial Implementation**
   - Screen capture setup
   - Basic overlay window
   - Unit template storage system
   - Configuration management

### Phase 2: Core Functionality
1. **Unit Recognition**
   - Template matching implementation
   - Unit level detection
   - Position tracking
   - Confidence scoring

2. **Data Processing**
   - Unit pool tracking logic
   - Board state management
   - Data validation and error handling

3. **Overlay Development**
   - Real-time display updates
   - User interface components
   - Data visualization

### Phase 3: Refinement
1. **Performance Optimization**
   - Capture interval tuning
   - Recognition algorithm optimization
   - Memory management
   - CPU/GPU utilization

2. **Accuracy Improvements**
   - Template matching refinement
   - Error correction
   - Edge case handling

3. **User Experience**
   - Customizable settings
   - Error feedback
   - Performance metrics

## Technical Requirements

### Required Libraries
- `mss`: Screen capture
- `opencv-python`: Image processing
- `PyQt5`: Overlay UI
- `numpy`: Array operations
- `pillow`: Image handling
- `pytest`: Testing framework

### System Requirements
- Windows 10/11
- Python 3.8+
- Minimum 4GB RAM
- DirectX 11 compatible GPU

## Potential Challenges and Solutions

### 1. Screen Capture Performance
- **Challenge**: High CPU usage during capture
- **Solution**: 
  - Implement frame buffering
  - Optimize capture regions
  - Use hardware acceleration where available

### 2. Unit Recognition Accuracy
- **Challenge**: False positives in unit detection
- **Solution**:
  - Implement confidence thresholds
  - Use multiple recognition methods
  - Add validation checks

### 3. Overlay Performance
- **Challenge**: UI lag during updates
- **Solution**:
  - Implement update batching
  - Use efficient rendering techniques
  - Optimize data structures

## Future Enhancements
1. Multi-player tracking
2. Advanced statistics and analytics
3. Game state prediction
4. Custom overlay themes
5. Export functionality for data analysis

## Testing Strategy
1. Unit tests for core functionality
2. Performance benchmarks
3. Accuracy testing with sample games
4. User testing for UI/UX feedback

## Documentation
1. Installation guide
2. User manual
3. API documentation
4. Contribution guidelines 

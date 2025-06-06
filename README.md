# Smart Parking and ALPR System at ASU

## Overview
This project aims to provide a comprehensive solution for efficient parking management at Arizona State University (ASU) by integrating Computer Vision (CV) technology and Automated License Plate Recognition (ALPR). The solution uses existing infrastructure to monitor real-time parking space availability and automate entry/exit for permit holders.

## Key Features:
- **Real-Time Parking Monitoring**: 
  - The system uses computer vision models to continuously track parking bay occupancy.
  - Leveraging OpenCV to define parking spaces and detect occupancy in real time.
  - Matplotlib is used to visually highlight available spaces.

- **License Plate Recognition (ALPR)**: 
  - The system utilizes YOLOv8 to detect license plates and EasyOCR for text recognition.
  - Enables automatic vehicle access without manual ticketing by verifying permit details through license plate matching.

- **Mobile App Integration**:
  - Displays real-time space availability on a mobile app.
  - Users can reserve parking spots before arrival and receive directions to the closest available spot.

- **Automated Gate Access**:
  - Using license plate recognition, permit holders can pass through entry barriers without needing to stop and scan a ticket.

## Benefits:
- **Cost-Effective**: 
  - The solution leverages existing cameras and infrastructure, reducing the need for additional hardware.
  
- **Scalable**: 
  - The system can be expanded to cover multiple campuses at ASU using the current camera network, making it capable of handling growing student populations and traffic volumes.

- **Self-Improving**: 
  - The system continuously retrains its computer vision models with new data, improving parking detection accuracy and adaptability over time.

## Technical Implementation:
- **Parking Spot Detection**:
  - OpenCV is used to define parking spaces and detect occupancy.
  - Data is stored using Pickle, marking the location of available and occupied spots.
  - Real-time updates of available spaces are shown using Matplotlib.

- **License Plate Recognition**:
  - YOLOv8 detects and locates vehicle plates.
  - EasyOCR reads the license plate text, facilitating automatic entry/exit verification.

- **User Application**:
  - Integration with a user-friendly mobile app that shows available spaces, recommends the best parking options, and allows for reservations.
  
- **Cloud Server**:
  - Data from the camera systems and parking space availability is processed in real time and updated to the cloud for seamless app integration.

## Risk and Privacy Management:
- **Bias and Detection Challenges**:
  - Variability in plate styles (e.g., different state or country plates) and environmental factors (e.g., weather or lighting) may impact detection accuracy.
  - **Mitigation**: Train models with diverse datasets and add fallback options for misreads.

- **Ethical and Privacy Concerns**:
  - License plate data could contain personally identifiable information, raising privacy concerns.
  - **Mitigation**: Data is encrypted, only stored for the session, and not shared with third parties without user consent.

- **Security Considerations**:
  - Risk of system manipulation or unauthorized access.
  - **Mitigation**: Implement strong cybersecurity measures, including regular system audits and hardening of models against adversarial attacks.


For any questions, feel free to reach out!

---

## How It Works:
1. **Monitor**: Parking cameras track occupancy, and gate cameras capture license plates.
2. **Analyze**: Computer vision models detect free spots and verify permits.
3. **Process**: Cloud server processes data and updates the app in real time.
4. **Connect**: The mobile app shows available spaces and grants gate access.

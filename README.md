# Exercise 5: Demonstrating Access Contention Problems in a Multitasking System

This project demonstrates how FreeRTOS is used to manage multiple tasks accessing shared resources in a multitasking system. LEDs serve as activity indicators for each task and highlight conflicts in accessing shared resources.

---

## **Diagram Task**

---

## **Required Hardware**
- **STM32F103C8T6** Microcontroller
- LEDs (Green, Red, Yellow)

---

## **Required Software**
- **STM32CubeIDE**
- **FreeRTOS**

---

## **How It Works**

### **Initialization and Task Scheduling**
- The program starts the **FreeRTOS kernel** to manage the execution of multiple threads.
- Tasks are assigned different priorities to reflect system requirements.

### **Mutual Exclusion (Shared Resource Management)**
- Two tasks, **GreenTask** and **RedTask**, alternate in accessing a shared variable `StartFlag`.
- **Critical sections** are implemented to protect the shared resource and prevent simultaneous access by both tasks.
- If a task fails to access the resource (due to the resource being in use), the **yellow LED** lights up to indicate a conflict.

### **Conflict Access Indicator**
- **With Critical Section**: Tasks access the shared resource alternately without conflicts.
- **Without Critical Section**: Access conflicts occur more frequently, causing the yellow LED to light up often.

---

## **LED Behavior**

| LED Color | Behavior |
|-----------|----------|
| **Green** | Lights up when the **GreenTask** accesses the shared resource. |
| **Red**   | Lights up when the **RedTask** accesses the shared resource. |
| **Yellow**| Lights up when a **conflict** occurs during resource access. |

---

### **LED Behavior Cycles**
- **Normal Case**: 
  - Green and red LEDs light up alternately, indicating conflict-free access to the shared resource.
- **Conflict Case**:
  - The yellow LED lights up frequently, indicating improper handling of the critical section and access conflicts.

---

## **Hardware Overview**


---

## **Demo Video**
https://drive.google.com/file/d/1FiC5l4lBiK5Kw7IRXF-mAMbihvpTKphv/view?usp=sharing

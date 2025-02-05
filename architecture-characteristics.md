
# Architecture Characteristics

> [!NOTE]
> These characteristics are based off the [business case and requirements](requirements.md).

## Driving Characteristics

1. **Data Integrity** (Top 3): Ensuring accurate data is crucial for monitoring patient vital signs in a hospital.
2. **Responsiveness** (Top 3): Timely data and alerts are essential for effective medical responses.
3. **Fault Tolerance** (Top 3): All system components must continue functioning even if individual parts encounter errors.
4. **Testability**: Rigorous testing is vital to ensure bug-free solutions in critical health care applications.
5. **Extensibility**: Future-proofing by adding devices for new patient measurements.
6. **Configurability**: Nurses need to configure patient-device and device-nurse station connections.
7. **Adaptability**: Preparing for the integration of additional vital devices in the future.

## System Characteristics

1. **Availability**: The system must remain accessible at all times to be effective.

## Other Considerations

1. **Interoperability**: Although extensive integration with external systems is not required, some interaction with existing company products will be necessary.
2. **Concurrency**: The system must handle data from up to 8 monitoring devices per patient and 500 patients simultaneously without delays.
3. **Scalability**: While the system's limits are well-defined, it should accommodate variable numbers of monitoring devices and allow for future additions.

## Supporting Information

- [Architecture Characteristics WorkSheet](adr/supportingDocuments/architecture-characteristics-worksheet.pptx)

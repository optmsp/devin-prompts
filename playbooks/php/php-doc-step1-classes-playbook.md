Hi Devin! This playbook will guide you through Phase 1 of documenting PHP code, focusing specifically on class-level documentation.

### Prerequisites
- Access to the target PHP project folder
- Knowledge of PHP documentation standards (refer to "PHP Code Documentation KB" in your knowledge base)
- Understanding of PHPDoc standards

### Instructions

1. **Initial Setup**
   ```bash
   # List and count all PHP files
   find . -type f -name "*.php" > php_files.txt
   wc -l php_files.txt > total_php_files.txt  # Save total file count
   ```

   Note: The total number of files saved in `total_php_files.txt` will be used later to ensure all files are documented.

2. **Class Documentation Process**
   For each class:

   ```php
   /**
    * [Brief class description]
    *
    * [Detailed explanation of class purpose and functionality]
    * Focus on the class's overall responsibility and role in the system.
    * Describe what problem it solves and how it fits into the application.
    * Do not document methods or properties in this phase.
    */
   ```

3. **Phase 1 Documentation Checklist**
   For each class:
   - [ ] Class has clear, concise description
   - [ ] Class's purpose and responsibility is well documented
   - [ ] Documentation follows no-prefix rule (avoid "Description:" or "Summary:")
   - [ ] Documentation is focused on class-level concerns only
   - [ ] Documentation explains class's role in the application
   - [ ] Documentation helps new developers understand the system

4. **Example Documentation**
   ```php
   <?php

   /**
    * User Authentication Service
    *
    * A comprehensive authentication service that manages user access and
    * security within the application. This class serves as the central
    * authority for all authentication-related operations, ensuring
    * consistent and secure user authentication across the entire system.
    *
    * The service is designed with security best practices in mind and
    * integrates seamlessly with the application's user management and
    * authorization systems. It provides a robust foundation for handling
    * user authentication while maintaining flexibility for different
    * authentication methods.
    */
   class AuthenticationService
   {
       // Methods and properties will be documented in later phases
   }
   ```

5. **File Tracking**
   1. Note the total number of files in `php_files.txt` (see `total_php_files.txt`).
   2. As you document each class, mark it with a checklist or record it in a "documented_files.txt".
   3. Compare the length of `documented_files.txt` vs. `total_php_files.txt` at the end:
      - If they differ, locate the missing files, document them, and repeat until all files are documented.

6. **Validation**
   - Review each documented class
   - Ensure documentation is clear and helpful
   - Verify all checklist items are complete
   - Ensure that the count of documented files matches the count in `total_php_files.txt`
   - If any files are missing, repeat the documentation for those files until the counts match
   - Get approval before proceeding to Phase 2

Remember:
- Focus only on class-level documentation in this phase
- Methods and properties will be documented in Phase 2
- Get approval before proceeding to the next phase


Need help? Refer to the "PHP Code Documentation KB" in your knowledge base for detailed guidelines and best practices.

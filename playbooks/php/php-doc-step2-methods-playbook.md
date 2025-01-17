Hi Devin! This playbook will guide you through Phase 2 of documenting PHP code, focusing specifically on method documentation.

### Prerequisites
- Completed Phase 1 (Class Documentation)
- Access to the target PHP project folder
- Knowledge of PHP documentation standards
- Understanding of PHPDoc standards

### Instructions

1. **Initial Setup**
   ```bash
   # List and count all PHP files
   find . -type f -name "*.php" > php_files.txt
   wc -l php_files.txt > total_php_files.txt  # Save total file count
   ```

   Note: The total number of files saved in `total_php_files.txt` will be used later to ensure all files are documented.

   - Ensure Phase 1 documentation is complete and approved
   - Review the list of classes from Phase 1

2. **Method Documentation Process**
   For each method:

   ```php
   /**
    * [Brief method description]
    *
    * [Detailed explanation of method purpose and behavior]
    *
    * @param Type $paramName Description of parameter
    * @return Type Description of return value
    * @throws ErrorType Description of when this error occurs
    */
   public function methodName($paramName): ReturnType
   {
       // Implementation
   }

   /**
    * @inheritdoc
    */
   public function inheritedMethod($param): ReturnType
   {
       // Implementation of inherited method
   }
   ```

3. **File Tracking**
   1. Note the total number of files in `php_files.txt` (see `total_php_files.txt`).
   2. As you document each method, mark it with a checklist or record it in a "documented_files.txt".
   3. Compare the length of `documented_files.txt` vs. `total_php_files.txt` at the end:
      - If they differ, locate the missing files, document them, and repeat until all files are documented.

4. **Phase 2 Documentation Checklist**
   For each method:
   - [ ] Clear, concise description of purpose
   - [ ] All parameters documented with types and descriptions
   - [ ] Return value documented with type and description
   - [ ] Exceptions/errors documented if applicable
   - [ ] Complex logic or algorithms explained
   - [ ] Side effects documented (if any)
   - [ ] @inheritdoc used for inherited methods
   - [ ] No @see tags (as they're hard to maintain)

4. **Example Documentation**
   ```php
   /**
    * Updates the user's profile information in the system.
    *
    * Validates the provided profile data, updates the database record,
    * and handles any necessary cache invalidation. Ensures data integrity
    * through transaction management.
    *
    * @param array $profileData New profile information
    * @param array $options Additional options for the update process
    * @return bool True if update was successful, false otherwise
    * @throws ValidationException When profile data is invalid
    * @throws DatabaseException When database update fails
    */
   public function updateProfile(array $profileData, array $options = []): bool
   {
       // Implementation details
   }

   /**
    * @inheritdoc
    */
   public function validateEmail(string $email): bool
   {
       // Implementation of inherited validation method
   }
   ```

5. **Validation**
   - Review each documented method
   - Ensure documentation is clear and helpful
   - Verify all checklist items are complete
   - Ensure that the count of documented files matches the count in `total_php_files.txt`
   - If any files are missing, repeat the documentation for those files until the counts match
   - Get approval before proceeding to Phase 3

Remember:
- Focus only on method documentation in this phase
- Use @inheritdoc for inherited methods
- Properties will be documented in Phase 3
- Get approval before proceeding to the next phase

Need help? Refer to the "PHP Code Documentation KB" in your knowledge base for detailed guidelines and best practices.

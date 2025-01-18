Hi Devin! This playbook will guide you through Phase 2 of documenting React code, focusing specifically on method and hook documentation.

### Prerequisites
- Completed Phase 1 (Component Documentation)
- Access to the target React project folder
- Knowledge of React documentation standards

### Instructions

1. **Initial Setup**
   ```bash
   # List and count all React component files
   find . -type f -name "*.jsx" -o -name "*.tsx" > components.txt
   wc -l components.txt > total_react_components.txt  # Save total file count
   ```

   Note: The total number of files saved in `total_react_components.txt` will be used later to ensure all files are documented.

   - Ensure Phase 1 documentation is complete and approved
   - Review the list of components from Phase 1

2. **Method and Hook Documentation Process**
   For each component's methods and hooks:

   ```jsx
   /**
    * [Brief method/hook description]
    *
    * @param {Type} paramName - Parameter description
    * @returns {Type} Description of the return value
    * @throws {ErrorType} Description of when this error occurs
    */
   const methodName = (paramName) => {
     // Implementation
   };

   /**
    * [Brief hook description]
    *
    * @param {Type} dependency - Dependency description
    * @returns {[Type, Function]} Array containing state and update function
    */
   const useCustomHook = (dependency) => {
     // Implementation
   };
   ```

3. **File Tracking**
   1. Note the total number of files in `components.txt` (see `total_react_components.txt`).
   2. As you document each method and hook, mark it with a checklist or record it in a "documented_files.txt".
   3. Compare the length of `documented_files.txt` vs. `total_react_components.txt` at the end:
      - If they differ, locate the missing files, document them, and repeat until all files are documented.

4. **Phase 2 Documentation Checklist**
   For each method/hook:
   - [ ] Clear, concise description of purpose
   - [ ] All parameters documented with types and descriptions
   - [ ] Return value documented with type and description
   - [ ] Exceptions/errors documented if applicable
   - [ ] Complex logic or algorithms explained
   - [ ] Side effects documented (if any)
   - [ ] Dependencies documented for hooks

4. **Example Documentation**
   ```jsx
   /**
    * Handles user profile updates and manages the update process.
    * 
    * Validates the profile data, communicates with the backend,
    * and manages loading/error states during the update process.
    *
    * @param {Object} profileData - New profile information
    * @param {string} profileData.name - User's full name
    * @param {string} profileData.email - User's email address
    * @param {Object} [options={}] - Optional update configuration
    * @returns {Promise<boolean>} True if update successful, false otherwise
    * @throws {ValidationError} When profile data is invalid
    */
   const handleProfileUpdate = async (profileData, options = {}) => {
     // Implementation details
   };

   /**
    * Custom hook for managing user profile data and updates.
    * 
    * Provides state management and update functionality for user profiles,
    * including loading states, error handling, and data persistence.
    *
    * @param {string} userId - The ID of the user to manage
    * @returns {[Object, Function]} [profile, updateProfile] Profile data and update function
    */
   const useProfile = (userId) => {
     // Implementation details
   };
   ```

5. **Validation**
   - Review each documented method and hook
   - Ensure documentation is clear and helpful
   - Verify all checklist items are complete
   - Ensure that the count of documented files matches the count in `total_react_components.txt`
   - If any files are missing, repeat the documentation for those files until the counts match
   - Get approval before proceeding to Phase 3

Remember:
- Focus only on method and hook documentation in this phase
- Props will be documented in Phase 3
- Get approval before proceeding to the next phase

Need help? Refer to the "React Code Documentation KB" in your knowledge base for detailed guidelines and best practices.

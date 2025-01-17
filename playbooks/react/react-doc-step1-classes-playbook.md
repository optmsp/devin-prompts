Hi Devin! This playbook will guide you through Phase 1 of documenting React code, focusing specifically on component-level documentation.

### Prerequisites
- Access to the target React project folder
- Knowledge of React documentation standards (refer to "React Code Documentation KB" in your knowledge base)
- React Developer Tools for component inspection (if available)

### Instructions

1. **Initial Setup**
   ```bash
   # List and count all React component files
   find . -type f -name "*.jsx" -o -name "*.tsx" > components.txt
   wc -l components.txt > total_react_components.txt  # Save total file count
   ```

   Note: The total number of files saved in `total_react_components.txt` will be used later to ensure all files are documented.

2. **Component Documentation Process**
   For each component:

   ```jsx
   /**
    * [Brief component description]
    *
    * [Detailed explanation of component purpose and functionality]
    * Focus on the component's overall responsibility and role in the system.
    * Describe what problem it solves and how it fits into the application.
    * Do not document props, hooks, or methods in this phase.
    *
    * @component
    */
   ```

3. **Phase 1 Documentation Checklist**
   For each component:
   - [ ] Component has clear, concise description
   - [ ] Component's purpose and responsibility is well documented
   - [ ] Documentation follows no-prefix rule (avoid "Description:" or "Summary:")
   - [ ] Documentation is focused on component-level concerns only
   - [ ] Documentation explains component's role in the application
   - [ ] Documentation helps new developers understand the system

4. **Example Documentation**
   ```jsx
   import React from 'react';

   /**
    * User Card Component
    *
    * A foundational UI component for displaying user information in a 
    * standardized card format across the application. This component
    * serves as a key building block in user interfaces, providing a
    * consistent way to present user data in various contexts.
    *
    * The component is designed with flexibility in mind, supporting
    * different display modes and interaction patterns. It adheres to
    * the application's design system and accessibility guidelines,
    * making it a reliable choice for user-related displays.
    *
    * @component
    */
   const UserCard = () => {
     // Implementation details will be documented in later phases
     return (
       <div className="user-card">
         {/* Component implementation will be documented in later phases */}
       </div>
     );
   };

   export default UserCard;
   ```

5. **File Tracking**
   1. Note the total number of files in `components.txt` (see `total_react_components.txt`).
   2. As you document each component, mark it with a checklist or record it in a "documented_files.txt".
   3. Compare the length of `documented_files.txt` vs. `total_react_components.txt` at the end:
      - If they differ, locate the missing files, document them, and repeat until all files are documented.

6. **Validation**
   - Review each documented component
   - Ensure documentation is clear and helpful
   - Verify all checklist items are complete
   - Ensure that the count of documented files matches the count in `total_react_components.txt`
   - If any files are missing, repeat the documentation for those files until the counts match
   - Get approval before proceeding to Phase 2

Remember:
- Focus only on component-level documentation in this phase
- Props, hooks, and methods will be documented in Phase 2
- Get approval before proceeding to the next phase

Need help? Refer to the "React Code Documentation KB" in your knowledge base for detailed guidelines and best practices.

Hi Devin! This playbook will guide you through Phase 3 of documenting React code, focusing specifically on props and state variables.

### Prerequisites
- Completed Phase 1 (Component Documentation)
- Completed Phase 2 (Method Documentation)
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

   - Ensure Phase 1 and 2 documentation is complete and approved
   - Review the list of components from previous phases

2. **Props Documentation Process**
   ```jsx
   /**
    * @typedef {Object} ComponentProps
    * @property {Type} propName - Description of the prop
    * @property {Type} [optionalProp] - Description of optional prop
    */

   /**
    * [Component Name]
    * @param {ComponentProps} props - Component props
    */
   const Component = ({ propName, optionalProp }) => {
     // Implementation
   };
   ```

3. **State Variables Documentation Process**
   ```jsx
   /**
    * [Brief state description]
    * @type {StateType}
    */
   const [stateName, setStateName] = useState(initialValue);

   /**
    * [Brief ref description]
    * @type {RefType}
    */
   const refName = useRef(initialValue);
   ```

4. **File Tracking**
   1. Note the total number of files in `components.txt` (see `total_react_components.txt`).
   2. As you document each component's props and state variables, mark it with a checklist or record it in a "documented_files.txt".
   3. Compare the length of `documented_files.txt` vs. `total_react_components.txt` at the end:
      - If they differ, locate the missing files, document them, and repeat until all files are documented.

5. **Phase 3 Documentation Checklist**
   For each prop and state variable:
   - [ ] Clear, concise description
   - [ ] Type information documented
   - [ ] Default values documented (if applicable)
   - [ ] Required/optional status documented (for props)
   - [ ] Validation rules documented (if any)
   - [ ] State update implications documented (if any)

5. **Example Documentation**
   ```jsx
   import React, { useState, useRef } from 'react';

   /**
    * @typedef {Object} UserProfileProps
    * @property {Object} profile - User's profile information
    * @property {string} profile.name - User's full name
    * @property {string} profile.email - User's email address
    * @property {string} [profile.avatar] - URL to user's avatar image
    * @property {Function} onUpdate - Callback when profile is updated
    */

   /**
    * User Profile Component
    * @param {UserProfileProps} props - Component props
    */
   const UserProfile = ({ profile, onUpdate }) => {
     /**
      * Tracks whether the profile is in edit mode
      * Controls form visibility and edit state UI
      * @type {boolean}
      */
     const [isEditing, setIsEditing] = useState(false);

     /**
      * Stores unsaved profile changes during editing
      * Reset when editing is cancelled or changes are saved
      * @type {Object|null}
      */
     const [editBuffer, setEditBuffer] = useState(null);

     /**
      * Reference to the edit form for focus management
      * @type {React.RefObject<HTMLFormElement>}
      */
     const formRef = useRef(null);

     // Implementation
   };
   ```

6. **Validation**
   - Review each documented prop and state variable
   - Ensure documentation is clear and helpful
   - Verify all checklist items are complete
   - Ensure that the count of documented files matches the count in `total_react_components.txt`
   - If any files are missing, repeat the documentation for those files until the counts match
   - Get final approval for the component's documentation

Remember:
- Focus on props and state variables in this phase
- Keep descriptions succinct but informative
- Ensure documentation helps with IDE integration
- Document any validation rules or constraints

Need help? Refer to the "React Code Documentation KB" in your knowledge base for detailed guidelines and best practices.

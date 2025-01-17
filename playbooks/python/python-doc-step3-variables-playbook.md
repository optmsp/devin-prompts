Hi Devin! This playbook will guide you through Phase 3 of documenting Python code, focusing specifically on module-level variables and class attributes.

### Prerequisites
- Completed Phase 1 (Module/Class Documentation)
- Completed Phase 2 (Method Documentation)
- Access to the target Python project folder
- Knowledge of Python documentation standards
- Understanding of PEP 257 and PEP 484

### Instructions

1. **Initial Setup**
   ```bash
   # List and count all Python files
   find . -type f -name "*.py" > python_files.txt
   wc -l python_files.txt > total_python_files.txt  # Save total file count
   ```

   Note: The total number of files saved in `total_python_files.txt` will be used later to ensure all files are documented.

   - Ensure Phase 1 and 2 documentation is complete and approved
   - Review the list of modules/classes from previous phases

2. **Module-Level Variables Documentation Process**
   ```python
   """Module docstring (already documented in Phase 1)"""

   #: Brief description of the constant
   #: Type information and additional details
   MODULE_CONSTANT: Type = value

   # For module-level variables that may change
   """Brief description of the variable
   Type information and additional details
   """
   module_var: Type = initial_value
   ```

3. **Class Attributes Documentation Process**
   ```python
   class ExampleClass:
       """Class docstring (already documented in Phase 1)"""

       #: Brief description of class variable
       #: Type information and additional details
       class_var: Type = value

       def __init__(self):
           """Constructor docstring (already documented in Phase 2)"""
           #: Brief description of instance attribute
           #: Type information and additional details
           self.instance_attr: Type = value
   ```

4. **File Tracking**
   1. Note the total number of files in `python_files.txt` (see `total_python_files.txt`).
   2. As you document each variable and attribute, mark it with a checklist or record it in a "documented_files.txt".
   3. Compare the length of `documented_files.txt` vs. `total_python_files.txt` at the end:
      - If they differ, locate the missing files, document them, and repeat until all files are documented.

5. **Phase 3 Documentation Checklist**
   For each variable/attribute:
   - [ ] Clear, concise description
   - [ ] Type hints included (PEP 484)
   - [ ] Default values documented (if applicable)
   - [ ] Scope and mutability documented
   - [ ] Validation rules documented (if any)
   - [ ] Side effects documented (if any)

5. **Example Documentation**
   ```python
   from typing import Dict, List, Optional
   from datetime import datetime

   #: Maximum number of retry attempts for API calls
   #: Configured based on service reliability metrics
   MAX_RETRIES: int = 3

   #: Default timeout for external service calls (in seconds)
   DEFAULT_TIMEOUT: float = 30.0

   class UserManager:
       """Class docstring (documented in Phase 1)"""

       #: Default user roles assigned to new accounts
       #: List of role identifiers from the authorization system
       default_roles: List[str] = ['basic_user']

       #: Cache timeout for user data (in seconds)
       #: Set to 0 to disable caching
       cache_timeout: int = 300

       def __init__(self):
           """Constructor docstring (documented in Phase 2)"""
           
           #: Dictionary mapping user IDs to their last activity timestamp
           #: Updated on every user action for session management
           self.last_activity: Dict[int, datetime] = {}

           #: Current number of active user sessions
           #: Thread-safe counter, use atomic operations
           self._active_sessions: int = 0

           #: Configuration for user preferences
           #: None if preferences haven't been loaded
           self.preferences: Optional[Dict[str, str]] = None
   ```

6. **Validation**
   - Review each documented variable and attribute
   - Ensure documentation is clear and helpful
   - Verify all checklist items are complete
   - Ensure that the count of documented files matches the count in `total_python_files.txt`
   - If any files are missing, repeat the documentation for those files until the counts match
   - Get final approval for the module's documentation

Remember:
- Focus on variables and attributes in this phase
- Keep descriptions succinct but informative
- Ensure documentation helps with IDE integration
- Document any validation rules or constraints

Need help? Refer to the "Python Code Documentation KB" in your knowledge base for detailed guidelines and best practices.

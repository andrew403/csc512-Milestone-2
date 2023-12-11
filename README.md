# Course Project Milestone-2

## Members
- Yung Hsuan Teng
- Jo Hao Huang

### LLVM Build Exploration

After encountering challenges in building LLVM from the source code, we explored alternative methods. One successful approach was installing LLVM directly through the Brew package manager, which proved to be a more straightforward process. However, our commitment to understanding the intricacies led us to continue attempting to build LLVM from the source code.

1. **Build Attempt:**
   - Configured the LLVM project using the following cmake command:
     ```bash
     cmake -S llvm -B build -G Ninja -DCMAKE_BUILD_TYPE=Debug
     ```
   - Executed the Ninja build command:
     ```bash
     ninja -C build check-llvm
     ```
   - The build appeared to be successful, but testing revealed expected failures.

2. **Clang Testing:**
   - Ran tests using Clang, and results were positive, indicating normal functionality.

3. **Next Steps:**
   - Uncertain whether the testing failures are significant or if a rebuild is necessary.
   - Seeking guidance on potential adjustments to address any identified issues.

### New Pass Development

In alignment with project goals, we began building a new pass following the instructions provided in the [LLVM documentation](https://llvm.org/docs/WritingAnLLVMNewPMPass.html).

1. **Pass Creation:**
   - Created a header file at:
     ```
     llvm/include/llvm/Transforms/Utils/HelloWorld.h
     ```
   - Added the corresponding cpp file at:
     ```
     llvm/lib/Transforms/Utils/HelloWorld.cpp
     ```

2. **Pass Execution:**
   - With all required pass contents in place, executed the pass using the command:
     ```bash
     ninja -C build/ opt
     ```
   - Ran the LLVM IR file `a.ll` through the pass to observe its behavior.

---
Please see the [google doc](https://docs.google.com/document/d/1pMxT-yqt-2UEmdBbyd9fecUfFnQ-fM-auqkFlpNCAD8/edit?usp=sharing) for the full content.

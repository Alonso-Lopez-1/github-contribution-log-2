# github-contribution-log-2

# Contribution [#9426]: [Don't hide the "Auto Assign Parts" on "Build Order > Line Items" page]

**Contribution Number:** [2]  
**Student:** [Alonso Lopez]  
**Issue:** [[https://github.com/inventree/InvenTree/issues/9426](https://github.com/inventree/InvenTree/issues/9426)]  
**Status:** [Phase I] [In Progress]

---

## Why I Chose This Issue

I chose issue #9426 because it is a clear user interface improvement, similar to the previous one I worked on, that further expands on the full-stack experience I am looking to gain. Most of my experience has been stronger on the backend and data side, so working on another frontend issue will help me sharpen the skills I gained from the first issue.

From reading the issue thread, I understand that this issue has a practical impact because keeping the “Auto Allocate Stock” button visible, even when disabled, would make the build order allocation workflow clearer and help users understand what steps are needed before parts can be allocated. I left a comment on the thread but have not received a response, so I will provide updates once I hear back.

---

## Understanding the Issue

### Problem Description

The "Auto Allocate Stock" button is hidden when a build order has not yet been issued. Because the button is not visible, users receive no indication of why allocation is unavailable or what action they must take first. This can make the workflow confusing for new users.

### Expected Behavior

The "Auto Allocate Stock" button should always be visible. When allocation is unavailable, the button should appear disabled and provide a tooltip explaining why it cannot be used and how to enable it by issuing or reissuing the build order.

### Current Behavior

I reproduced the current behavior using the latest development version of InvenTree. Since this issue was opened, the UI has changed. The "Line Items" tab is now named "Required Parts", and the application now includes separate "Allocated Stock" and "Consumed Stock" tabs. The second requested improvement appears to have already been implemented, as clicking Auto Allocate with no selected parts now assumes all parts should be allocated. However, the first requested improvement remains unresolved because the Auto Allocate button is still hidden while the build order is pending and no tooltip explains why allocation is unavailable.

### Affected Components

Based on reproducing the issue, I expect the affected components to be the Build Order Required Parts page and the frontend components responsible for rendering the Auto Allocate Stock action and its enabled/disabled state. I will identify the specific files before implementation.

---

## Reproduction Process

### Environment Setup

I used the existing InvenTree development container that I configured during my previous contribution. Since the environment was already working, no additional setup issues were encountered. I updated my fork, created a new feature branch, and verified that the latest development version reproduced the behavior.

### Steps to Reproduce

- Start the InvenTree development environment.
- Create or open a Build Order that is still in the Pending state.
- Navigate to the Required Parts tab.
- Observe that the Auto Allocate Stock button is not displayed.
- Issue the Build Order.
- Observe that the Auto Allocate Stock button now appears.
- Click Auto Allocate Stock without selecting any parts.
- Observe that allocation proceeds for all parts, indicating the second requested improvement has already been implemented.

### Reproduction Evidence

- **Commit showing reproduction:** Not created yet. I am waiting for maintainer confirmation that the remaining behavior should still be implemented before creating a feature branch.
- **Screenshots/logs:** <img width="1917" height="966" alt="image" src="https://github.com/user-attachments/assets/b1ed4074-1f6a-466a-a19c-2db51ad88b75" />
<img width="1918" height="967" alt="image" src="https://github.com/user-attachments/assets/205497a8-a2f5-4d92-9b45-aac72d85038f" />

- **My findings:** The issue seems to be partially completed. The automatic allocation behavior when no parts are selected has already changed.

---

## Solution Approach

### Analysis

The issue appears to be partially resolved since it was originally reported. The automatic allocation behavior when no parts are selected has already changed. However, the UI still removes the Auto Allocate action entirely when the build order is pending rather than showing a disabled action with guidance for the user.

### Proposed Solution

If the maintainer confirms this behavior should still be addressed, I plan to modify the frontend so the Auto Allocate Stock action remains visible while disabled whenever allocation cannot be performed. A tooltip or similar explanatory message would describe why the action is unavailable and how to enable it.

### Implementation Plan

Using UMPIRE framework (adapted):

**Understand:** Reference "Understanding the issue" above

**Match:** I plan to look for similar disabled action buttons elsewhere in the Build Order interface so the implementation remains consistent with the existing UI.

**Plan:** 
1. Identify the component that renders the Auto Allocate button.
2. Determine why the button is hidden instead of disabled.
3. Modify the rendering logic to keep the button visible.
4. Add a tooltip explaining why allocation is unavailable.
5. Verify that issued Build Orders continue to behave normally.

**Implement:** 

**Review:** Compare the implementation against CONTRIBUTING.md and existing UI patterns before opening a pull request.

**Evaluate:** Verify that pending Build Orders display a disabled Auto Allocate button with guidance, while issued Build Orders continue to allow allocation. Confirm that existing allocation behavior is unchanged.

---

## Testing Strategy

### Unit Tests

- [ ] Test case 1: [Description]
- [ ] Test case 2: [Description]
- [ ] Test case 3: [Description]

### Integration Tests

- [ ] Integration scenario 1
- [ ] Integration scenario 2

### Manual Testing

[What you tested manually and results]

---

## Implementation Notes

### Week [X] Progress

[What you built this week, challenges faced, decisions made]

### Week [Y] Progress

[Continue documenting as you work]

### Code Changes

- **Files modified:** [List]
- **Key commits:** [Links to important commits]
- **Approach decisions:** [Why you chose certain approaches]

---

## Pull Request

**PR Link:** [GitHub PR URL when submitted]

**PR Description:** [Draft or final PR description - much of the content above can be adapted]

**Maintainer Feedback:**
- [Date]: [Summary of feedback received]
- [Date]: [How you addressed it]

**Status:** [Awaiting review / Iterating / Approved / Merged]

---

## Learnings & Reflections

### Technical Skills Gained

[What you learned technically]

### Challenges Overcome

[What was hard and how you solved it]

### What I'd Do Differently Next Time

[Reflection on your process]

---

## Resources Used

- [Link to helpful documentation]
- [Tutorial or Stack Overflow post that helped]
- [GitHub issues or discussions that helped]

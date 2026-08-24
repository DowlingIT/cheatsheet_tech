---
title: Testing
subtopic: react
group: Testing & Tooling
order: 1
---

#### React Testing Library

```jsx
import { render, screen, fireEvent } from '@testing-library/react';

test('increments on click', () => {
  render(<Counter />);
  fireEvent.click(screen.getByRole('button', { name: /\+1/i }));
  expect(screen.getByText('1')).toBeInTheDocument();
});
```

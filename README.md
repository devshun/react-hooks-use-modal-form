# **use-modal-form**

simplifies the implementation of formatted modals

<br />

## **Usage**

```
import React, { useState, useCallback } from 'react';
import { createRoot } from 'react-dom/client';
import { useModal } from 'react-hooks-use-modal-form';
import { LoginForm } form "./Login"

const App = () => {
  const [renderModal, open] = useModalForm({
    formComponent: LoginForm
  });

  const onClick = useCallback(() => {
    open({
      // form default values
      formDefaultValues: { name: "", email: "" },
      // form submit function
      onSubmit: onSubmit,
      // Function to run if submission fails
      onError: onError
    })
  }, [open])

  return (
    <div>
      <p>Modal is Open? {isOpen ? 'Yes' : 'No'}</p>
      <button onClick={open}>OPEN</button>
      <Modal>
        <div>
          <h1>Title</h1>
          <p>This is a customizable modal.</p>
          <button onClick={close}>CLOSE</button>
        </div>
      </Modal>
    </div>
  );
};

const root = createRoot(document.getElementById('root'));
root.render(<App />);
```

# `@typed-themes/typed`

> Typed System Default Theme

`yarn add @typed-themes/typed`

## Usage

```tsx
import * as React from "react"
import { ThemeProvider, GlobalStyles } from "@typed-system/typed-system"
import theme from "@typed-themes/typed"

export const App: React.FC = ({ children }) => {
  return (
    <ThemeProvider $theme={theme}>
      <>
        <GlobalStyles />
        {children}
      </>
    </ThemeProvider>
  )
}

```

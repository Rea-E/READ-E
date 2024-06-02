# READ-Enpx create-react-app story-app
cd story-app
npm install axios react-router-dom @emotion/styled @emotion/react
story-app/
├── public/
├── src/
│   ├── components/
│   │   ├── auth/
│   │   │   ├── Login.js
│   │   │   ├── Register.js
│   │   ├── layout/
│   │   │   ├── Navbar.js
│   │   │   ├── Sidebar.js
│   │   │   ├── Footer.js
│   │   ├── stories/
│   │   │   ├── StoryList.js
│   │   │   ├── StoryUpload.js
│   │   │   ├── StoryPage.js
│   │   ├── genres/
│   │   │   ├── GenreManagement.js
│   │   ├── Home.js
│   ├── context/
│   ├── App.js
│   ├── index.js
│   ├── utils/
│   │   ├── setAuthToken.js
├── package.json
// src/theme.js
export const theme = {
  colors: {
    primary: '#00bcd4',
    secondary: '#00838f',
    background: '#e0f7fa',
    text: '#000000',
    white: '#ffffff',
  },
  fonts: {
    main: 'Arial, sans-serif',
  },
};
// src/index.js
import React from 'react';
import ReactDOM from 'react-dom';
import { ThemeProvider } from '@emotion/react';
import App from './App';
import { theme } from './theme';
import './index.css';

ReactDOM.render(
  <ThemeProvider theme={theme}>
    <App />
  </ThemeProvider>,
  document.getElementById('root')
);
// src/components/layout/Navbar.js
/** @jsxImportSource @emotion/react */
import { css } from '@emotion/react';
import { Link } from 'react-router-dom';

const Navbar = () => {
  return (
    <nav
      css={css`
        background: ${theme.colors.primary};
        padding: 1rem;
        display: flex;
        justify-content: space-between;
        align-items: center;
      `}
    >
      <h1 css={css`color: ${theme.colors.white};`}>StoryApp</h1>
      <ul css={css`display: flex; list-style: none;`}>
        <li css={css`margin-right: 1rem;`}>
          <Link to="/" css={css`color: ${theme.colors.white}; text-decoration: none;`}>Home</Link>
        </li>
        <li css={css`margin-right: 1rem;`}>
          <Link to="/login" css={css`color: ${theme.colors.white}; text-decoration: none;`}>Login</Link>
        </li>
        <li>
          <Link to="/register" css={css`color: ${theme.colors.white}; text-decoration: none;`}>Register</Link>
        </li>
      </ul>
    </nav>
  );
};

export default Navbar;
// src/components/layout/Sidebar.js
/** @jsxImportSource @emotion/react */
import { css } from '@emotion/react';
import { Link } from 'react-router-dom';

const Sidebar = () => {
  return (
    <aside
      css={css`
        width: 250

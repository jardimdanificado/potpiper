## Usage

### Importing the Library

```javascript
import { PipeSession } from 'potpiper';
```

### Initializing a Session

To start a session, you can create an instance of `PipeSession`:

```javascript
const session = new PipeSession(execPath, args);
```

- `execPath`: The path to the executable.
- `args` : Arguments.

### Sending Commands

You can send commands to the process and receive the results using the `send` method:

```javascript
const result = await session.send("your_code_here");
```

### Closing the Session

Don't forget to close the session when you're done:

```javascript
session.close();
```

## Example

Here's a simple example of how to use `potpiper` with lua:

```javascript
import { PipeSession } from 'potpiper';

const lua = new PipeSession('luajit');

(async () => {
  const result = await lua.send('print("this is a test")');
  console.log(result);
  lua.close();
})();
```

## License

This project is licensed under the [GNU General Public License version 3 (GPL-3.0)](https://www.gnu.org/licenses/gpl-3.0.html).

- You are free to use, modify, and distribute this software.
- Any derivative work based on this software must also be released under the GPLv3.
- This software is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.
- You should have received a copy of the GNU General Public License along with this program. If not, see [https://www.gnu.org/licenses/](https://www.gnu.org/licenses/).

By using this software, you agree to comply with the terms of the GNU General Public License version 3.

## Acknowledgments

- [LuaJIT](https://luajit.org/): The Lua Just-In-Time Compiler used in this project.
- [json.lua](https://github.com/rxi/json.lua): The JSON lib used in this project.
# jest-test
some jest tips
```javascript
// Module to test
/* const request = require('request-promise')
async function doAsync() {
  const res = await request.get('https://jsonplaceholder.typicode.com/users')
  return res
}
module.exports = doAsync */

const request = require('request-promise')
const ok = require('./ok')

describe('nothing', () => {
  it('should nothing', async () => {
    const spy42 = jest.spyOn(request, 'get').mockImplementation(() => 42)
    ok()
    expect(spy42).toBeCalled()
    spy42.mockRestore()
    const result = await ok()
    expect(JSON.parse(result)).toHaveLength(10)
  })
})

```

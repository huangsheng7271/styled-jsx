# Snapshot report for `test/plugins.js`

The actual snapshot is saved in `plugins.js.snap`.

Generated by [AVA](https://avajs.dev).

## applies plugins

> Snapshot 1

    `import _JSXStyle from "styled-jsx/style";␊
    import styles from './styles';␊
    const color = 'red';␊
    export default (() => <div className={\`jsx-${styles.__hash}\` + " " + _JSXStyle.dynamic([["2799750516", [color, otherColor]]])}>␊
        <p className={\`jsx-${styles.__hash}\` + " " + _JSXStyle.dynamic([["2799750516", [color, otherColor]]])}>test</p>␊
        <_JSXStyle id={"2799750516"} dynamic={[color, otherColor]}>{\`span.${color}.__jsx-style-dynamic-selector{color:${otherColor};}\`}</_JSXStyle>␊
        <_JSXStyle id={styles.__hash}>{styles}</_JSXStyle>␊
      </div>);`

## babel-test plugin strips jsx attribute

> Snapshot 1

    `import styles from './styles';␊
    const color = 'red';␊
    export default (() => <div>␊
        <p>test</p>␊
        <style>{\`␊
          div.${color} {␊
            color: ${otherColor};␊
          }␊
        \`}</style>␊
        <style>{styles}</style>␊
      </div>);`

## passes options to plugins

> Snapshot 1

    `import _JSXStyle from "styled-jsx/style";␊
    import styles from './styles';␊
    const color = 'red';␊
    export default (() => <div className={\`jsx-${styles.__hash}\` + " " + _JSXStyle.dynamic([["2799750516", [color, otherColor]]])}>␊
        <p className={\`jsx-${styles.__hash}\` + " " + _JSXStyle.dynamic([["2799750516", [color, otherColor]]])}>test</p>␊
        <_JSXStyle id={"2799750516"} dynamic={[color, otherColor]}>{".test.__jsx-style-dynamic-selector{content:\\"{\\"foo\\":false,\\"babel\\":{\\"location\\":{\\"start\\":{\\"line\\":7,\\"column\\":16},\\"end\\":{\\"line\\":11,\\"column\\":5}},\\"vendorPrefixes\\":false,\\"sourceMaps\\":false,\\"isGlobal\\":false}}\\";}"}</_JSXStyle>␊
        <_JSXStyle id={styles.__hash}>{styles}</_JSXStyle>␊
      </div>);`

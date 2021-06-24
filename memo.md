# コマンド
- npm run dev  
Starts the development server.

- npm run build  
Builds the app for production.

- npm start  
Runs the built app in production mode.

# ファイル
- next-env.d.ts  
タイプ定義。削除も編集もしてはいけない。

- additional.d.ts  
新しくタイプを追加。tsconfig.jsonでincludeする。

# Next.jsの型
## Static Generation and Server-side Renderingための型
```ts
import { GetStaticProps, GetStaticPaths, GetServerSideProps } from 'next'
export const getStaticProps: GetStaticProps = async (context) => {}
```

## APIのための型
```ts
import type { NextApiRequest, NextApiResponse } from 'next'

export default (req: NextApiRequest, res: NextApiResponse) => {
  res.status(200).json({ name: 'John Doe' })
}

type Data = {
  name: string
}

export default (req: NextApiRequest, res: NextApiResponse<Data>) => {
  res.status(200).json({ name: 'John Doe' })
}
```

https://nextjs.org/docs/basic-features/typescript#custom-app

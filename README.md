# Deploy len Vercel (chi file build, khong co ma nguon)

## Buoc 1 — Day len GitHub

1. Tao repo moi tren GitHub (private).
2. Push **toan bo noi dung folder nay** len repo (khong co thu muc con, file nam ngay root).

```bash
git init
git add .
git commit -m "Initial deploy"
git branch -M main
git remote add origin https://github.com/<ten-khach>/<ten-repo>.git
git push -u origin main
```

## Buoc 2 — Ket noi Vercel

1. [vercel.com/new](https://vercel.com/new) → Import Git Repository.
2. Chon repo vua push.
3. **Framework Preset:** Other (hoac de Vercel tu nhan dien static).
4. **Build Command:** de trong hoac `npm run build` (script chi echo, khong build lai).
5. **Output Directory:** de trong (root).
6. Deploy.

## Buoc 3 — Kiem tra

- Mo `https://<domain-vercel>/contact/`
- Test proxy: `https://<domain-vercel>/vps-health` → `{"status":"ok"}`
- F12 → Network → filter `socket.io` → polling `200`

## Backend VPS

Frontend da cau hinh proxy socket qua `vercel.json` toi:

`http://103.167.151.113:3000`

Neu doi IP/port VPS, sua `vercel.json` (cac dong `destination`) roi push lai.

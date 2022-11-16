## Pengenalan Database Migration
- Database migration memudahkan proses migrasi database saat membangun aplikasi
- Proses migrasi database diantaranya yaitu menambah tabel, mengubah tabel, menghubungkan tabel, dll
- Memudahkan tim untuk berkolaborasi dalam membangun perubahan struktur database

## GoLang Migrate
- Golang Migrate adalah salah satu tool Database Migration yang populer dan digunakan oleh programmer Golang
- Mendukung banyak database: MySQL PostgresQL, Sqlite, Mongodb dll
- Repo: https://github.com/golang-migrate/migrate

## Menginstall Golang Migrate
- `go install -tags "database1,database2" github.com/golang-migrate/migrate/v4/cmd/migrate@latest`
- `tags` digunakan untuk memilih satu database atau lebih
- **Contoh**: `go install -tags "postgres,mysql" github.com/golang-migrate/migrate/v4/cmd/migrate@latest`
## Pengenalan Database Migration
- Database migration memudahkan proses migrasi database saat membangun aplikasi
- Proses migrasi database diantaranya yaitu menambah tabel, mengubah tabel, menghubungkan tabel, dll
- Memudahkan tim untuk berkolaborasi dalam membangun perubahan struktur database

## GoLang Migrate
- Golang Migrate adalah salah satu tool Database Migration yang populer dan digunakan oleh programmer Golang
- Mendukung banyak database: MySQL PostgresQL, Sqlite, Mongodb dll
- Repo: https://github.com/golang-migrate/migrate

## Menginstall Golang Migrate
- `go install -tags 'database1,database2' github.com/golang-migrate/migrate/v4/cmd/migrate@latest`
- `tags` digunakan untuk memilih satu database atau lebih
- **Contoh**: `go install -tags 'postgres,mysql' github.com/golang-migrate/migrate/v4/cmd/migrate@latest`
- Saat menginstall golang migrate, executable file di folder $GOPATH/bin/ terdapat pada folder migrate. File tersebut adalah aplikasi golang migrate yang akan digunakan untuk membuat database migration
- Saat menjalankan file `migrate`, akan muncul help seperti berikut.

```cmd
$ migrate
Usage: migrate OPTIONS COMMAND [arg...]
       migrate [ -version | -help ]

Options:
  -source          Location of the migrations (driver://url)
  -path            Shorthand for -source=file://path
  -database        Run migrations against this database (driver://url)
  -prefetch N      Number of migrations to load in advance before executing (default 10)
  -lock-timeout N  Allow N seconds to acquire database lock (default 15)
  -verbose         Print verbose logging
  -version         Print version
  -help            Print usage

Commands:
  create [-ext E] [-dir D] [-seq] [-digits N] [-format] [-tz] NAME
           Create a set of timestamped up/down migrations titled NAME, in directory D with extension E.
           Use -seq option to generate sequential up/down migrations with N digits.
           Use -format option to specify a Go time format string. Note: migrations with the same time cause "duplicate migration version" error.
           Use -tz option to specify the timezone that will be used when generating non-sequential migrations (defaults: UTC).

  goto V       Migrate to version V
  up [N]       Apply all or N up migrations
  down [N] [-all]    Apply all or N down migrations
        Use -all to apply all down migrations
  drop [-f]    Drop everything inside database
        Use -f to bypass confirmation
  force V      Set version V but don't run migration (ignores dirty state)
  version      Print current migration version

Source drivers: file
Database drivers: mysql, postgres, postgresql, stub
```
- bagian database drivers adalah driver - driver database yang sudah terinstall

## Membuat Database Migration
`migrate create -ext sql -dir db/migrations <nama_file_migration>`
- `ext` extension: Bisa sql dan json
- `dir` directory: Tempat menyimpan file migration
- `<nama_file_migration>`: nama file migration
- Output: 2 file sesuai dengan `ext`. 
  - Berakhiran .up: Untuk membuat migration up
  - Berakhiran .down: Untuk membuat migration down

## Migration Up
- File migration untuk mengeksekusi kode program di file .up

## Migration Down
- File migration untuk mengeksekusi kode program di file .down
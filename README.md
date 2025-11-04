<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    <!-- Bootstrap -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css"/>

    <!-- DataTables -->
    <link rel="stylesheet" href="https://cdn.datatables.net/1.11.3/css/dataTables.bootstrap.min.css"/>
    <link rel="stylesheet" href="https://cdn.datatables.net/fixedheader/3.2.0/css/fixedHeader.bootstrap.min.css"/>
    <link rel="stylesheet" href="https://cdn.datatables.net/responsive/2.2.9/css/responsive.bootstrap.min.css"/>
    
    <!-- DataTables Buttons (UNTUK PRINT) -->
    <link rel="stylesheet" href="https://cdn.datatables.net/buttons/2.4.1/css/buttons.bootstrap.min.css"/>

    <title>KODE ICD 10 TAHUN 2010 DAN IM (INDONESIA MODIFICATION)</title>

    <style>
      body {
        background-color: #3e2f1c; /* coklat tua gelap */
        color: #f5e9d3; /* warna teks krem terang */
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      }

      .container {
        background-color: rgba(60, 42, 23, 0.85); /* coklat semi-transparan */
        padding: 20px 30px;
        border-radius: 12px;
        box-shadow: 0 0 15px rgba(0,0,0,0.6);
      }

      h3, h4 {
        color: #f5e9d3;
        font-weight: 600;
      }

      /* Styling tabel DataTables agar semua coklat dan teks krem */
      table.dataTable {
        background-color: #5a4223 !important; /* coklat medium */
        color: #f5e9d3 !important;
        border: 1px solid #7a5931 !important; /* border coklat */
      }

      table.dataTable thead th {
        background-color: #7a5931 !important; /* coklat header */
        color: #f5e9d3 !important;
        border-bottom: 2px solid #a17e46 !important;
      }

      table.dataTable tbody td {
        background-color: #5a4223 !important;
        color: #f5e9d3 !important;
        border: 1px solid #6c4e26 !important;
      }

      table.dataTable tbody tr:nth-child(even) td {
        background-color: #654b27 !important; /* baris genap */
      }

      table.dataTable tbody tr:hover td {
        background-color: #886b3e !important;
        color: #fff !important;
      }

      /* Hilangkan garis putih default pada border tabel */
      table.dataTable,
      table.dataTable th,
      table.dataTable td {
        border-collapse: collapse !important;
        border-style: solid !important;
        border-color: #7a5931 !important;
      }

      /* Tombol print */
      .dt-button {
        background-color: #7a5931 !important;
        color: #f5e9d3 !important;
        border: none !important;
        border-radius: 5px;
        padding: 5px 15px;
        font-weight: 600;
      }

      .dt-button:hover {
        background-color: #a17e46 !important;
        color: #fff !important;
      }

      /* Link hilangkan underline */
      a {
        color: #f5e9d3;
        text-decoration: none;
      }

      a:hover {
        text-decoration: underline;
      }

      /* Print styling supaya tetap coklat */
      @media print {
        body {
          background-color: #3e2f1c !important;
          color: #f5e9d3 !important;
        }
        table.dataTable {
          background-color: #5a4223 !important;
          color: #f5e9d3 !important;
          border: 1px solid #7a5931 !important;
        }
        table.dataTable thead th {
          background-color: #7a5931 !important;
          color: #f5e9d3 !important;
          border-bottom: 2px solid #a17e46 !important;
        }
        table.dataTable tbody td {
          background-color: #5a4223 !important;
          color: #f5e9d3 !important;
          border: 1px solid #6c4e26 !important;
        }
        table.dataTable tbody tr:nth-child(even) td {
          background-color: #654b27 !important;
        }
        table.dataTable tbody tr:hover td {
          background-color: #886b3e !important;
          color: #fff !important;
        }
        .dt-button {
          display: none !important; /* sembunyikan tombol saat print */
        }
      }
    </style>
  </head>

  <body>
    <div class="container">
      <div class="row">
        <div class="col-lg-12 col-md-12 col-sm-12 col-xs-12">
          <h3 class="text-center mb-4">KODE ICD 10 TAHUN 2010 DAN IM (INDONESIA MODIFICATION)</h3>
          <h4 class="text-center mb-4" id="packageName"></h4>

          <!-- TABEL -->
          <table
            id="example"
            class="table table-striped table-bordered mt-2 mb-2"
            style="width: 100%"
          ></table>

          <br><br>
          <p id="passingGrade"></p>
        </div>
      </div>
    </div>

    <!-- JS Libraries -->
    <script src="https://code.jquery.com/jquery-3.5.1.js"></script>
    <script src="https://cdn.datatables.net/1.11.3/js/jquery.dataTables.min.js"></script>
    <script src="https://cdn.datatables.net/1.11.3/js/dataTables.bootstrap.min.js"></script>
    <script src="https://cdn.datatables.net/fixedheader/3.2.0/js/dataTables.fixedHeader.min.js"></script>
    <script src="https://cdn.datatables.net/responsive/2.2.9/js/dataTables.responsive.min.js"></script>
    <script src="https://cdn.datatables.net/responsive/2.2.9/js/responsive.bootstrap.min.js"></script>
    <script src="https://unpkg.com/sweetalert/dist/sweetalert.min.js"></script>

    <!-- DataTables Buttons JS -->
    <script src="https://cdn.datatables.net/buttons/2.4.1/js/dataTables.buttons.min.js"></script>
    <script src="https://cdn.datatables.net/buttons/2.4.1/js/buttons.bootstrap.min.js"></script>
    <script src="https://cdn.datatables.net/buttons/2.4.1/js/buttons.print.min.js"></script>

    <script type="text/javascript">
      $(document).ready(function () {
        $("#example").DataTable({
          ajax: "https://script.google.com/macros/s/AKfycbxrLuaGKckTnIo8U3TC1lxw8fXj6wLpJMA8LIrgvVximsNcyLorBbb6xifMAqoCwMYW/exec",
          dom: 'Bfrtip', // Tombol
          buttons: ['print'], // Tombol print

          columns: [
            {
              title: "No",
              data: null,
              render: function (data, type, row, meta) {
                return meta.row + 1; // Nomor urut otomatis
              },
              orderable: false,
              searchable: false
            },
            {
              title: "KODE ICD 10",
              data: "KODE ICD 10",
            },
            {
              title: "DESKRIPSI ICD 10",
              data: "DESKRIPSI ICD 10",
            },
            {
              title: "TERJEMAHAN ICD 10",
              data: "TERJEMAHAN ICD 10",
              
            }
          ],
          rowId: "KODE ICD 10 TAHUN 2010 DAN IM (INDONESIA MODIFICATION)",
          liveAjax: true
        });
      });
    </script>
  </body>
</html>

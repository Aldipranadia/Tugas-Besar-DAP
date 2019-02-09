program Tubes;

uses crt;
        type
                dataapartemen=record
                t_apartemen:string;
                harga:longint;
                stok:integer;
                fasilitas:string;
                luasbangunan:string;
                jumlahkamar:integer;
                end;
        type
                nama=record
                n_apartemen:string;
                no_apartemen:string;
                alamat_apartemen:string;
                tipe_apartemen:array[1..5] of dataapartemen;
                end;
        type
                list_apartemen=record
                nama_a:string;
                tipe_a:string;
                jumlah_a:integer;
                harga_a:longint;
                total_a:longint;
                end;
        type
                costumer=record
                n_costumer:string;
                tot_harga:longint;
                tot_trans:integer;
                d_costumer:array[1..99] of list_apartemen;
                end;
        type apartemen=array[1..5] of nama;
        type transaksi=array[1..99] of costumer;
var
        ar_apartment:apartemen;
        ar_trans:transaksi;
        nmax_t,nmax_ap:integer;
        pilihan:string;
        i,j,o,e:integer;

        function hitung(a,b:longint):longint;
        begin
          hitung:=a*b;
        end;
        procedure input(var ap:apartemen; var max_ap:integer);
        begin
                writeln('INPUT DATA');
                            writeln;
                                        j:=1;
                                        max_ap:=max_ap+1;
                                        if(max_ap<=5)then
                                        begin
                                        write('Nama Apartemen : ');
                                        readln(ap[max_ap].n_apartemen);
                                        write('Alamat apartemen : ');
                                        readln(ap[max_ap].alamat_apartemen);writeln;
                                        write('No Telp : ');
                                        readln(ap[max_ap].no_apartemen);
                                        repeat
                                                ap[max_ap].tipe_apartemen[1].t_apartemen:='Studio';
                                                ap[max_ap].tipe_apartemen[2].t_apartemen:='Convertible studio';
                                                ap[max_ap].tipe_apartemen[3].t_apartemen:='Loft';
                                                ap[max_ap].tipe_apartemen[4].t_apartemen:='Junior 1 bedroom';
                                                ap[max_ap].tipe_apartemen[5].t_apartemen:='Garden';
                                                writeln;
                                                write('Tipe ',ap[max_ap].tipe_apartemen[j].t_apartemen);
                                                writeln;
                                                write('Harga : ');
                                                readln(ap[max_ap].tipe_apartemen[j].harga);
                                                write('Stok : ');
                                                readln(ap[max_ap].tipe_apartemen[j].stok);
                                                write('Fasilitas : ');
                                                readln(ap[max_ap].tipe_apartemen[j].fasilitas);
                                                write('Luas Bangunan(KM persegi) : ');
                                                readln(ap[max_ap].tipe_apartemen[j].luasbangunan);
                                                write('Jumlah Kamar : ');
                                                readln(ap[max_ap].tipe_apartemen[j].jumlahkamar);
                                                j:=j+1;
                                        until(j>=6);
                                        writeln;
                                        writeln;
                                        writeln('                                               ***DATA TER-INPUT***');
                                end;
                                write('Press Enter untuk kembali ke menu utama');readln;

        end;


        procedure infoapartemen(ap:apartemen;max_ap:integer);
        var
          l,k:integer;
        begin
          if (max_ap=0) then
              begin
              writeln;
              writeln('****************************************************************');
              writeln('ANDA BELUM MENGINPUTKAN DATA,SILAHKAN INPUT DATA TERLEBIH DAHULU');
              writeln('****************************************************************');
              writeln;
              write('Press Enter untuk kembali ke menu utama');
              readln;
              clrscr;
              end
          else if (max_ap<>0) then
            begin
              writeln('==================================');
              writeln('----------INFO APARTEMEN----------');
              writeln('==================================');
          writeln;
          l:=1;
              repeat
                      writeln;
                      writeln('Nama Apartemen : ',ap[l].n_apartemen);
                      write('Alamat apartemen : ',ap[l].alamat_apartemen);
                      write(' | No Telp : ',ap[l].no_apartemen);
                      k:=1;
                      repeat
                              writeln;
                              write('Tipe Apartemen : ',ap[l].tipe_apartemen[k].t_apartemen);
                              write(' | Harga : RP.',ap[l].tipe_apartemen[k].harga);
                              write(' | Stok yang tersedia : ',ap[l].tipe_apartemen[k].stok);
                              write(' | Fasilitas : ',ap[l].tipe_apartemen[k].fasilitas);
                              write(' | Luas Bangunan : ',ap[l].tipe_apartemen[k].luasbangunan,' KM persegi');
                              write(' | Jumlah Kamar : ',ap[l].tipe_apartemen[k].jumlahkamar);
                              k:=k+1;
                      until(k>=6);
                      writeln;
                      l:=l+1;
              until(l>max_ap);
              writeln;
              write('Press Enter untuk kembali ke menu utama');readln;
              clrscr;
            end;
        end;


        procedure pembelianapartemen(var trans:transaksi;var ap:apartemen;var max_t:integer;max_ap:integer);
        var
          x:string;
          z,n,kluar,i:integer;
          anslist:string;
        begin
          if (max_ap=0) then
                  begin
                          writeln('****************************************************************');
                          writeln('MAAF KAMI BELUM BISA MENERIMA TRANSAKSI,SILAHKAN COBA LAGI NANTI');
                          writeln('****************************************************************');
                          writeln;
                          write('Press Enter untuk kembali ke menu utama');
                          readln;
                          clrscr;
                  end
          else if (max_ap<>0) then
                  begin
                          writeln('PEMBELIAN APARTEMEN');
                          writeln;
                          kluar:=0;
                          repeat
                                  write('Masukan nama costumer : ');
                                  readln(x);
                                  z:=1;
                                  if max_t<>0 then
                                  begin
                                    repeat
                                      if (x=trans[z].n_costumer) then
                                        begin
                                        kluar:=1;
                                        end
                                      else
                                        begin
                                        z:=z+1;
                                        end;
                                    until (z>max_t) or (kluar=1);
                                    if kluar = 0 then
                                    begin
                                      max_t:=max_t+1;
                                      trans[max_t].n_costumer:=x;
                                      z:=max_t;
                                    end;
                                  end
                                  else
                                  begin
                                    max_t:=max_t+1;
                                    trans[max_t].n_costumer:=x;
                                    z:=max_t;
                                  end;
                                  writeln;
                                  repeat
                                    trans[z].tot_trans:=trans[z].tot_trans+1;
                                    writeln('=DAFTAR APARTEMEN 2017=');
                                    if (max_ap<>0) then
                                      begin
                                        for i:= 1 to max_ap do
                                          begin
                                            writeln(i,'.',ap[i].n_apartemen);
                                          end;
                                      end;
                                    writeln;
                                    write('Masukan nama apartemen : ');
                                    readln(trans[z].d_costumer[trans[z].tot_trans].nama_a);
                                    for n:=1 to 5 do
                                      begin
                                          if(trans[z].d_costumer[trans[z].tot_trans].nama_a=ap[n].n_apartemen) then
                                                  begin
                                                          writeln;
                                                          writeln('=TIPE APARTEMEN=');
                                                          writeln('1.Studio');
                                                          writeln('2.Convertible studio');
                                                          writeln('3.Loft');
                                                          writeln('4.Junior 1 bedroom');
                                                          writeln('5.Garden');
                                                          writeln;
                                                          write('Masukan tipe dari apartemen ',ap[n].n_apartemen,' : ');
                                                          readln(trans[z].d_costumer[trans[z].tot_trans].tipe_a);
                                                          for o:=1 to 5 do
                                                                  begin
                                                                  if(trans[z].d_costumer[trans[z].tot_trans].tipe_a=ap[n].tipe_apartemen[o].t_apartemen) then
                                                                          begin
                                                                                  writeln('Harga satuan : RP.',ap[n].tipe_apartemen[o].harga);
                                                                                  write('Jumlah di beli : ');
                                                                                  readln(trans[z].d_costumer[trans[z].tot_trans].jumlah_a);
                                                                                  trans[z].d_costumer[trans[z].tot_trans].total_a:=hitung(ap[n].tipe_apartemen[o].harga,trans[z].d_costumer[trans[z].tot_trans].jumlah_a);
                                                                                  ap[n].tipe_apartemen[o].stok:=ap[n].tipe_apartemen[o].stok-trans[z].d_costumer[trans[z].tot_trans].jumlah_a;
                                                                                  writeln('Anda harus membayar :',trans[z].d_costumer[trans[z].tot_trans].total_a);
                                                                          end;
                                                                  end;
                                                  writeln;
                                                  end;
                                      end;
                                          write('Mau menambah pembelian apartemen?[Y/N] : ');
                                          readln(anslist);
                                          clrscr;
                                  until((anslist='n')or(anslist='N')or(trans[z].tot_trans=99));
                                  writeln;
                                  write('Mau melakukan transaksi lain?[Y/N] : ');
                                  readln(anslist);
                                  clrscr;
                          until((anslist='n')or(anslist='N'));
                          clrscr;
                  end;
        end;


        procedure infotransaksi(ap:apartemen;trans:transaksi;max_t:integer);
        var
          p,q,z,i,id:integer;
          f:boolean;
          pay:longint;
          nama_costumer:string;
        begin
          if (max_t=0) then
              begin
                      writeln('*****************************************************');
                      writeln('MAAF ANDA BELUM MENGINPUTKAN DATA PEMBELIAN APARTEMEN');
                      writeln('*****************************************************');
                      writeln;
                      write('Press Enter untuk kembali ke menu utama');
                      readln;
                      clrscr;
              end
          else
              if (max_t<>0) then
                      begin
                              pay:=0;
                              f:=FALSE;
                              writeln('INFO TRANSAKSI COSTUMER');
                              write('Masukan data costumer : ');
                              readln(nama_costumer);
                              for z:=1 to 99 do
                                begin
                                  if (nama_costumer=trans[z].n_costumer) then
                                    id:=z;
                                end;
                              writeln;
                              p:=1;
                                      repeat
                                          if(nama_costumer=trans[p].n_costumer) then
                                            begin
                                            clrscr;
                                            f:=TRUE;
                                            q:=1;
                                            repeat
                                                writeln('==================================');
                                                writeln('----------INFO TRANSAKSI----------');
                                                writeln('==================================');
                                                writeln('Apartemen yang di beli : ',trans[p].d_costumer[q].nama_a);
                                                writeln('Tipe Apartemen : ',trans[p].d_costumer[q].tipe_a);
                                                for i:=1 to 5 do
                                                begin
                                                  for j:=1 to 5 do
                                                  begin
                                                    if (ap[i].n_apartemen=trans[p].d_costumer[q].nama_a) then
                                                      begin
                                                        if (ap[i].tipe_apartemen[j].t_apartemen=trans[p].d_costumer[q].tipe_a) then
                                                          begin
                                                            writeln('Harga satuan : RP.',ap[i].tipe_apartemen[j].harga);
                                                          end;
                                                      end;
                                                  end;
                                                end;
                                                writeln('Jumlah di beli : ',trans[p].d_costumer[q].jumlah_a);
                                                writeln;
                                                q:=q+1;
                                            until(q>trans[p].tot_trans);
                                            writeln;
                                            end;
                                        p:=p+1;
                                      until(p>max_t);
                                      if (f=TRUE) then
                                        begin
                                          for i:=1 to 99 do
                                            begin
                                              pay:=pay+trans[id].d_costumer[i].total_a;
                                            end;
                                          writeln('Total belanja saudara ',nama_costumer,' = RP.',pay);
                                        end
                                      else if (f=FALSE) then
                                        begin
                                          writeln('Data costumer tidak di temukan')
                                        end;
                      readln;
                      clrscr;
                      end;
        end;

        procedure exit;
        begin
          writeln('                                                ===TERIMA KASIH===');
          writeln('                                             ==ATAS KEPERCAYAAN ANDA==');
        end;

        procedure searchdata(var ap:apartemen;var idk:integer;max_ap:integer);
        var
          a:integer;
          search:string;
        begin
          writeln('=DAFTAR APARTEMEN 2017=');
          if (max_ap<>0) then
            begin
              for i:= 1 to max_ap do
                begin
                  writeln(i,'.',ap[i].n_apartemen);
                end;
            end;
          writeln;
          write('Masukan nama apartemen : ');
          readln(search);
          for a:=1 to 5 do
            begin
              if (search=ap[a].n_apartemen) then
                begin
                  writeln;
                  writeln('Nama Apartemen : ',ap[a].n_apartemen);
                  writeln('Alamat apartemen : ',ap[a].alamat_apartemen);
                  writeln('No Telp : ',ap[a].no_apartemen);
                  idk:=a;
                end;
            end;
        end;

        procedure searchdeletedata(var ap:apartemen;var idk:integer;max_ap:integer);
        var
          a:integer;
          search:string;
        begin
          writeln('=DAFTAR APARTEMEN 2017=');
          if (max_ap<>0) then
            begin
              for i:= 1 to max_ap do
                begin
                  writeln(i,'.',ap[i].n_apartemen);
                end;
            end;
          writeln;
          write('Masukan nama apartemen : ');
          readln(search);
          for a:=1 to 5 do
            begin
              if (search=ap[a].n_apartemen) then
                begin
                  idk:=a;
                end;
            end;
        end;



        procedure edit(var ap:apartemen;max_ap:integer);
        var
          j:integer;
          i:integer;
        begin
          if (max_ap=0) then
              begin
              writeln('****************************************************************');
              writeln('ANDA BELUM MENGINPUTKAN DATA,SILAHKAN INPUT DATA TERLEBIH DAHULU');
              writeln('****************************************************************');
              writeln;
              write('Press Enter untuk kembali ke menu utama');
              readln;
              clrscr;
              end
          else if (max_ap<>0) then
            begin
            clrscr;
            writeln('EDIT DATA');
            writeln;
              j:=1;
              searchdata(ap,i,max_ap);
              repeat
                    ap[i].tipe_apartemen[1].t_apartemen:='Studio';
                    ap[i].tipe_apartemen[2].t_apartemen:='Convertible studio';
                    ap[i].tipe_apartemen[3].t_apartemen:='Loft';
                    ap[i].tipe_apartemen[4].t_apartemen:='Junior 1 bedroom';
                    ap[i].tipe_apartemen[5].t_apartemen:='Garden';
                    writeln;
                    write('Tipe ',ap[i].tipe_apartemen[j].t_apartemen);
                    writeln;
                    write('Harga : ');
                    readln(ap[i].tipe_apartemen[j].harga);
                    write('Stok : ');
                    readln(ap[i].tipe_apartemen[j].stok);
                    write('Fasilitas : ');
                    readln(ap[i].tipe_apartemen[j].fasilitas);
                    write('Luas Bangunan(KM persegi) : ');
                    readln(ap[i].tipe_apartemen[j].luasbangunan);
                    write('Jumlah Kamar : ');
                    readln(ap[i].tipe_apartemen[j].jumlahkamar);
                    j:=j+1;
              until(j=6);
              clrscr;
              writeln('                                               ***DATA TER-UPDATE***');
              write('Press Enter untuk kembali ke menu utama');readln;
            end;
        end;

        procedure deletedata(var ap:apartemen;var max_ap:integer);
        var
          i,j:integer;
        begin
          if (max_ap=0) then
              begin
              writeln('****************************************************************');
              writeln('ANDA BELUM MENGINPUTKAN DATA,SILAHKAN INPUT DATA TERLEBIH DAHULU');
              writeln('****************************************************************');
              writeln;
              write('Press Enter untuk kembali ke menu utama');
              readln;
              clrscr;
              end
          else if (max_ap=1) then
            begin
              clrscr;
              writeln('DELETE DATA');
              writeln;
              writeln('Press Enter untuk menghapus data');
              readln;
              clrscr;
              writeln('==================================');
              writeln('----------DATA TERHAPUS-----------');
              writeln('==================================');
              writeln;
              writeln('Press Enter untuk kembali ke menu utama');
              readln;
              max_ap:=0;
            end
          else if (max_ap>1) then
            begin
              clrscr;
              writeln('DELETE DATA');
              writeln;
              searchdeletedata(ap,i,max_ap);
                repeat
                  ap[i].n_apartemen:=ap[i+1].n_apartemen;
                  ap[i].alamat_apartemen:=ap[i+1].alamat_apartemen;
                  ap[i].no_apartemen:=ap[i+1].no_apartemen;
                  j:=1;
                  repeat
                    ap[i].tipe_apartemen[j].t_apartemen:=ap[i+1].tipe_apartemen[j].t_apartemen;
                    ap[i].tipe_apartemen[j].harga:=ap[i+1].tipe_apartemen[j].harga;
                    ap[i].tipe_apartemen[j].stok:=ap[i+1].tipe_apartemen[j].stok;
                    ap[i].tipe_apartemen[j].fasilitas:=ap[i+1].tipe_apartemen[j].fasilitas;
                    ap[i].tipe_apartemen[j].luasbangunan:=ap[i+1].tipe_apartemen[j].luasbangunan;
                    ap[i].tipe_apartemen[j].jumlahkamar:=ap[i+1].tipe_apartemen[j].jumlahkamar;
                    j:=j+1;
                  until (j>5);
                  i:=i+1;
                until(i>max_ap);
                max_ap:=max_ap-1;
                writeln;
                writeln('Press Enter untuk menghapus data');
                readln;
                clrscr;
                writeln('==================================');
                writeln('----------DATA TERHAPUS-----------');
                writeln('==================================');
                writeln;
                writeln('Press Enter untuk kembali ke menu utama');
                readln;
            end;
        end;

        procedure sortdata(var ap:apartemen;max_ap:integer;e:integer);
        var
          i,j,min,id,k,l:integer;
          a:longint;
          b,c,d:string;
        begin
          if (max_ap=0) then
              begin
              writeln('****************************************************************');
              writeln('ANDA BELUM MENGINPUTKAN DATA,SILAHKAN INPUT DATA TERLEBIH DAHULU');
              writeln('****************************************************************');
              writeln;
              write('Press Enter untuk kembali ke menu utama');
              readln;
              clrscr;
              end
          else if (max_ap<>0) then
          begin
            searchdata(ap,id,max_ap);
            for i:=1 to e-1 do
              begin
                min:=i;
                for j:=i+1 to e do
                  begin
                    if(ap[id].tipe_apartemen[j].harga<ap[id].tipe_apartemen[min].harga) then
                      min:=j;
                  end;
                  //HARGA APARTEMEN
                  a:=ap[id].tipe_apartemen[min].harga;
                  ap[id].tipe_apartemen[min].harga:=ap[id].tipe_apartemen[i].harga;
                  ap[id].tipe_apartemen[i].harga:=a;
                  //TIPE APARTEMEN
                  b:=ap[id].tipe_apartemen[min].t_apartemen;
                  ap[id].tipe_apartemen[min].t_apartemen:=ap[id].tipe_apartemen[i].t_apartemen;
                  ap[id].tipe_apartemen[i].t_apartemen:=b;
                  //LUAS BANGUNAN
                  c:=ap[id].tipe_apartemen[min].luasbangunan;
                  ap[id].tipe_apartemen[min].luasbangunan:=ap[id].tipe_apartemen[i].luasbangunan;
                  ap[id].tipe_apartemen[i].luasbangunan:=c;
                  //FASILITAS
                  d:=ap[id].tipe_apartemen[min].fasilitas;
                  ap[id].tipe_apartemen[min].fasilitas:=ap[id].tipe_apartemen[i].fasilitas;
                  ap[id].tipe_apartemen[i].fasilitas:=d;
                  //JUMLAH KAMAR
                  k:=ap[id].tipe_apartemen[min].jumlahkamar;
                  ap[id].tipe_apartemen[min].jumlahkamar:=ap[id].tipe_apartemen[i].jumlahkamar;
                  ap[id].tipe_apartemen[i].jumlahkamar:=k;
                  //STOK APARTEMEN
                  l:=ap[id].tipe_apartemen[min].stok;
                  ap[id].tipe_apartemen[min].stok:=ap[id].tipe_apartemen[i].stok;
                  ap[id].tipe_apartemen[i].stok:=l;
                  end;
            writeln;
            clrscr;
            writeln('==================================');
            writeln('---------HASIL PENGURUTAN---------');
            writeln('==================================');
            writeln('Apartemen ',ap[id].n_apartemen);
            writeln;
            for i:= 1 to 5 do
              begin
                write('Tipe apartemen : ',ap[id].tipe_apartemen[i].t_apartemen);
                write(' | Stok yang tersedia : ',ap[id].tipe_apartemen[i].stok);
                write(' | Harga apartemen : ',ap[id].tipe_apartemen[i].harga);
                write(' | Fasilitas apartemen : ',ap[id].tipe_apartemen[i].fasilitas);
                write(' | Luas bangunan : ',ap[id].tipe_apartemen[i].luasbangunan,' KM persegi');
                write(' | Jumlah kamar : ',ap[id].tipe_apartemen[i].jumlahkamar);
                writeln;
                end;
            writeln;
            writeln('Press Enter untuk kembali ke menu utama');
            readln;
          end;
        end;

        procedure mainmenu;
        begin
                writeln('                                                  ==PRANADIA COMPANY==');
                writeln('                                                     HERE FOR GOOD');
                writeln('1. Input Data ');
                writeln('2. Update Data ');
                writeln('3. Info Aparatemen ');
                writeln('4. Daftar Harga Apartemen(Rendah-Tinggi)');
                writeln('5. Pembelian Apartamen ');
                writeln('6. Data Transaksi ');
                writeln('7. Exit ');
                writeln;
                write('Masukan Pilihan Anda : ');
                readln(pilihan);
                writeln;
                case pilihan of
                      '1':begin
                            clrscr;
                            input(ar_apartment,nmax_ap);
                            clrscr;
                            mainmenu;
                            end;
                        '2':begin
                            clrscr;
                            writeln('==UPDATE DATA==');
                            writeln;
                            writeln('1. Edit Data ');
                            writeln('2. Delete Data ');
                            writeln('3. Kembali ke Menu utama');
                            writeln;
                            write('Masukan pilihan anda : ');
                            readln(pilihan);
                            writeln;
                            case pilihan of
                                    '1':begin
                                        clrscr;
                                        edit(ar_apartment,nmax_ap);
                                        clrscr;
                                        mainmenu;
                                        end;
                                    '2':begin
                                        clrscr;
                                        deletedata(ar_apartment,nmax_ap);
                                        clrscr;
                                        mainmenu;
                                        end;
                                    '3':begin
                                        clrscr;
                                        mainmenu;
                                        end;
                                    end;
                            end;
                        '3':begin
                            clrscr;
                            infoapartemen(ar_apartment,nmax_ap);
                            clrscr;
                            mainmenu;
                            end;
                        '4':begin
                            clrscr;
                            e:=5;
                            sortdata(ar_apartment,nmax_ap,e);
                            clrscr;
                            mainmenu;
                            end;
                        '5':begin
                            clrscr;
                            pembelianapartemen(ar_trans,ar_apartment,nmax_t,nmax_ap);
                            clrscr;
                            mainmenu;
                            end;
                        '6':begin
                            clrscr;
                            infotransaksi(ar_apartment,ar_trans,nmax_t);
                            clrscr;
                            mainmenu;
                            end;
                        '7':begin
                            exit;
                            end;
                else
                        clrscr;
                        writeln('Input Not Valid');
                        writeln('Press Enter untuk kembali ke menu utama');readln;
                        clrscr;
                        mainmenu;
                end;
        end;
{=======================Program Utama=========================}
begin
clrscr;
        mainmenu;
readln;
end.

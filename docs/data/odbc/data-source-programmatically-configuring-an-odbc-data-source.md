---
title: 'Veri kaynağı: Program aracılığıyla ODBC veri kaynağını yapılandırma'
ms.date: 11/04/2016
f1_keywords:
- SQLConfigDataSource
helpviewer_keywords:
- ODBC data sources, configuring
- SQLConfigDataSource method example
- ODBC connections, configuring
- configuring ODBC data sources
ms.assetid: b8cabe9b-9e12-4d73-ae36-7cb12dee3213
ms.openlocfilehash: 33269b65835812a6e1a03e091833831781d97b6d
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037970"
---
# <a name="data-source-programmatically-configuring-an-odbc-data-source"></a>Veri kaynağı: Program aracılığıyla ODBC veri kaynağını yapılandırma

Bu konuda, açık veritabanı bağlantısı (ODBC) veri kaynağı adları program aracılığıyla nasıl yapılandırabileceğiniz açıklanmaktadır. Bu size esneklik verilere erişmek için açıkça ODBC Yöneticisi'ni veya diğer programları veri kaynaklarının adlarını belirtmek için kullanılacak kullanıcının zorlamadan sağlar.

Genellikle, bir kullanıcı, ilişkili veritabanı yönetim sistemi (DBMS) bu işlemi destekliyorsa, bir veri kaynağı oluşturmak için ODBC Yöneticisi çalışır.

ODBC Yöneticisi yoluyla bir Microsoft Access ODBC veri kaynağı oluştururken, iki seçenek sunulur: varolan bir .mdb dosyasını seçebilirsiniz veya yeni bir .mdb dosyası oluşturabilirsiniz. MFC ODBC uygulamanızdan .mdb dosyası oluşturmanın programlı hiçbir yolu yoktur. Uygulamanızın verilerini bir Microsoft Access veri kaynağına (.mdb dosyası) getirin gerektiriyorsa, bu nedenle, büyük olasılıkla kullanabilir veya ihtiyaç duyduğunuzda kopyalayın, bir boş bir .mdb dosyası bulundurmak istersiniz.

Ancak, birçok DBMS, programlı veri kaynağı oluşturmasına izin verir. Bazı veri kaynakları, veritabanları için bir dizin belirtimi korur. Diğer bir deyişle, bir dizin veri kaynağıdır ve veri kaynağındaki her tablo ayrı bir dosyada depolanır (dBASE durumunda her tablo bir .dbf dosyasıdır). Microsoft Access ve SQL Server gibi diğer ODBC veritabanlarının sürücüleri, veri kaynakları oluşturulmadan önce belirli bazı ölçütlerin karşılanmasını gerektirir. Örneğin, SQL Server ODBC sürücüsü kullanılırken, SQL Server bilgisayarı sağladıktan gerekir.

##  <a name="_core_sqlconfigdatasource_example"></a> SQLConfigDataSource örneği

Aşağıdaki örnekte `::SQLConfigDataSource` yeni bir Excel veri kaynağı oluşturmak için ODBC API işlevini çağırdı yeni Excel veri kaynağı:

```
SQLConfigDataSource(NULL,ODBC_ADD_DSN, "Excel Files (*.xls)",
                   "DSN=New Excel Data Source\0"
                   "Description=New Excel Data Source\0"
                   "FileType=Excel\0"
                   "DataDirectory=C:\\EXCELDIR\0"
                   "MaxScanRows=20\0");
```

Veri kaynağının aslında bir dizin (C:\EXCELDIR); olduğuna dikkat edin Bu dizinin var olması gerekir. Excel sürücüsü dizinleri (.xls dosyası başına bir tablo) bireysel tablolar gibi dosyaları ve veri kaynağı kullanır.

Tablo oluşturma hakkında daha fazla bilgi için bkz. [veri kaynağı: Program aracılığıyla ODBC veri kaynağında tablo oluşturma](../../data/odbc/data-source-programmatically-creating-a-table-in-an-odbc-data-source.md).

Aşağıdaki bilgiler ele alınmaktadır geçirilmesi gereken parametreler `::SQLConfigDataSource` ODBC API işlevi. Kullanılacak `::SQLConfigDataSource`, Odbcinst.h üstbilgi dosyasını eklemeniz ve Odbcinst.lib içeri aktarma kitaplığını kullanmanız gerekir. Ayrıca Odbccp32.dll çalışma süresi (veya 16 bit için Odbcinst.dll) yolu olmalıdır.

ODBC Yöneticisi'ni veya benzer bir yardımcı programını kullanarak bir ODBC veri kaynağı adı oluşturabilirsiniz. Ancak bazen bunu ayrı bir yardımcı programını çalıştırmak kullanıcının gerek kalmadan erişim elde etmek için doğrudan uygulamanızın içinden bir veri kaynağı adı oluşturmanız istenir.

ODBC Yöneticisi (genellikle Denetim Masası'ndaki yüklü), Windows kayıt defteri (veya 16 bit için Odbc.ini dosyasına) girişler ekleyerek yeni bir veri kaynağı oluşturur. ODBC Sürücü Yöneticisi veri kaynağı hakkında gerekli bilgileri almak için bu dosyayı sorgular. Hangi bilgilerin kayıt defterinde çağırarak sağlamanız gerektiğinden yerleştirilmesi gerektiğini bilmeniz önemlidir `::SQLConfigDataSource`.

Bu bilgiler olmadan doğrudan kayıt defterine yazılabilir rağmen `::SQLConfigDataSource`, bunu yapan herhangi bir uygulama verilerini korumak için Sürücü Yöneticisi'ni kullandığı mevcut tekniğe dayanır. Bu tekniği kullanan herhangi bir uygulama, daha sonraki bir düzeltmesi, veri kaynakları hakkında farklı bir yolla tutma ODBC Sürücü Yöneticisi uygulayan kaydı bozuk. Genellikle sağlandığında API işlevi kullanmanız önerilir. Örneğin, kullanırsanız kodunuz 16 bitten 32 bite taşınabilir `::SQLConfigDataSource` işlev Odbc.ini dosyasına veya kayıt defteri yazdığından işlev.

##  <a name="_core_sqlconfigdatasource_parameters"></a> SQLConfigDataSource parametreleri

Aşağıdaki parametreleri açıklar `::SQLConfigDataSource` işlevi. Bilgilerin çoğunu ODBC API'SİNDEN alınan *Programcının Başvurusu* Visual C++ sürüm 1.5 ve sonrası ile sağlanan.

###  <a name="_core_function_prototype"></a> İşlev prototipi

```
BOOL SQLConfigDataSource(HWND hwndParent,UINT fRequest, LPCSTR lpszDriver, LPCSTR lpszAttributes);
```

### <a name="remarks"></a>Açıklamalar

####  <a name="_core_parameters_and_usage"></a> Parametreleri ve kullanım

*hwndParent*<br/>
Yeni veri kaynağı hakkında kullanıcıdan sağladığı ek bilgi edinmek için oluşturan ODBC Sürücü Yöneticisi veya belirli ODBC sürücüsünün herhangi bir iletişim kutusunun sahibi olarak belirtilen pencere. Varsa *lpszAttributes* parametresi yeterli bilgi sağlamazsa, bir iletişim kutusu görüntülenir. *HwndParent* parametre NULL olabilir.

*IpszDriver*<br/>
Sürücü açıklaması. Bu, kullanıcılara fiziksel sürücü adı (DLL) yerine sunulan addır.

*lpszAttributes*<br/>
Biçimindeki özniteliklerin listesi "keyname = value". Bu dizeler, listenin sonundaki iki ardışık null sonlandırıcıyla beraber null sonlandırıcılar tarafından ayrılır. Bu öznitelikler, yeni veri kaynağı için kayıt defterine gidin öncelikle varsayılan sürücüye özel girişlerdir. Bu işlev için ODBC API başvurusunda belirtilmeyen önemli bir anahtar "yeni veri kaynağı adını belirten" DSN "DİR ("veri kaynağı adı"), ' dir. Girişlerin geri kalanı yeni veri kaynağına ilişkin sürücüye özel. Genellikle kullanıcı iletişim kutuları için yeni değerleri ile sürücü isteyebilir çünkü tüm girişlerin sağlamak gerekli değildir. (Ayarlayın *hwndParent* Bunu yapmak için null.) Kullanıcıdan istenmemesi için varsayılan değerleri açıkça sağlamak isteyebilirsiniz.

#### <a name="to-determine-the-description-of-a-driver-for-the-lpszdriver-parameter-using-odbc-administrator"></a>ODBC Yöneticisi'ni kullanarak IpszDriver parametresi için bir sürücünün tanımını belirlemek için

1. ODBC Yöneticisi çalıştırın.

1. **Ekle**'yi tıklatın.

Bu, yüklenen sürücülerin ve bunlara ilişkin açıklamaların listesini verir. Bu açıklama olarak kullanın *IpszDriver* parametresi. Bunlar, açıklamada yer alıyorsa dosya adı uzantısı ve parantezler dahil olmak üzere tüm Açıklama "Excel dosyaları (*.xls)" gibi kullanmanız gerektiğini unutmayın.

Alternatif olarak, kayıt defteri inceleyebilirsiniz (veya 16 bit Odbcinst.ini dosyasını), tüm sürücü girişlerini ve açıklamalarını "ODBC sürücüleri" kayıt defteri anahtarı altında (veya Odbcinst.ini içindeki [ODBC Drivers] bölümü) listesini içerir.

Anahtar adlarını ve değerleri bulmanın bir yolu *lpszAttributes* parametresi, bir önceden yapılandırılmış veri kaynağında (belki de bir ODBC Yöneticisi tarafından yapılandırılan) ilişkin Odbc.ini dosyasını incelemek için.

#### <a name="to-find-keynames-and-values-for-the-lpszattributes-parameter"></a>LpszAttributes parametresi için ve değerleri bulmak için

1. Windows Kayıt Defteri Düzenleyicisi'ni çalıştırın (veya 16 bit için Odbc.ini dosyasını açın).

1. Aşağıdakilerden birini kullanarak ODBC veri kaynakları bilgilerini bulun:

   - 32 bit için anahtarını bulun **HKEY_CURRENT_USER\Software\ODBC\ODBC. INI\ODBC Data Sources** sol bölmesinde.

      Sağ bölmede form girişlerini listeler: "pub: REG_SZ:*<data source name>*"burada *<data source name>* kullanmayı düşündüğünüz sürücü için istediğiniz ayarlarla önceden yapılandırılmış bir veri kaynağı. İstediğiniz veri kaynağı, örneğin, SQL Server'ı seçin. Dizesini izleyen öğeler "pub:" olan, sipariş, keyname ve değeri kullanmak için *lpszAttributes* parametresi.

   - 16 bit için Odbc.ini dosyasına tarafından işaretlenen bölümü bulun. [*\<veri kaynağı adı >*].

      Biçimidir bu satırı takip eden satırlar "keyname = value". Bunlar tam olarak kullanmak için girişler, *lpszAttributes* parametresi.

Kullanacağınız belirli bir sürücünün belgelerini incelemek isteyebilirsiniz. ODBC Yöneticisi'ni çalıştırarak erişebilirsiniz sürücü için çevrimiçi Yardım içinde yararlı bilgiler bulabilirsiniz. Bu Yardım dosyaları Windows NT, Windows 3.1 veya Windows 95 için genellikle WINDOWS\SYSTEM dizinine yerleştirilir.

#### <a name="to-obtain-online-help-for-your-odbc-driver"></a>ODBC sürücünüz için çevrimiçi Yardım almak için

1. ODBC Yöneticisi çalıştırın.

1. **Ekle**'yi tıklatın.

1. Sürücü adını seçin.

1. **Tamam**'ı tıklatın.

ODBC Yöneticisi belirli sürücü için yeni bir veri kaynağı oluşturmak amacıyla bilgileri görüntülediğinde, tıklayın **yardımcı**. Bu, genellikle sürücünün kullanımı hakkında önemli bilgiler içeren, belirli bir sürücünün Yardım dosyasını açar.

## <a name="see-also"></a>Ayrıca bkz.

[Veri Kaynağı (ODBC)](../../data/odbc/data-source-odbc.md)

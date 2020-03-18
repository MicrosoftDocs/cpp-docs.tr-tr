---
title: 'Veri Kaynağı: Program Aracılığıyla ODBC Veri Kaynağını Yapılandırma'
ms.date: 11/04/2016
f1_keywords:
- SQLConfigDataSource
helpviewer_keywords:
- ODBC data sources, configuring
- SQLConfigDataSource method example
- ODBC connections, configuring
- configuring ODBC data sources
ms.assetid: b8cabe9b-9e12-4d73-ae36-7cb12dee3213
ms.openlocfilehash: 38f0f383256a05c983fb7e7d7a498e16881c7b78
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446949"
---
# <a name="data-source-programmatically-configuring-an-odbc-data-source"></a>Veri Kaynağı: Program Aracılığıyla ODBC Veri Kaynağını Yapılandırma

Bu konuda, açık veritabanı bağlantısı (ODBC) veri kaynağı adlarını programlı bir şekilde nasıl yapılandırabileceğiniz açıklanmaktadır. Bu sayede, Kullanıcı, veri kaynaklarının adlarını belirtmek için ODBC Yöneticisi 'ni veya diğer programları açıkça kullanmayı zorunlu olmadan verilere erişim esnekliği sağlar.

Genellikle, bir Kullanıcı, ilişkili veritabanı yönetim sistemi (DBMS) bu işlemi destekliyorsa bir veri kaynağı oluşturmak için ODBC Yöneticisi 'ni çalıştırır.

ODBC Yöneticisi aracılığıyla bir Microsoft Access ODBC veri kaynağı oluştururken, iki seçenek sunulur: var olan bir. mdb dosyasını seçebilirsiniz veya yeni bir. mdb dosyası oluşturabilirsiniz. MFC ODBC uygulamanızdan. mdb dosyasını oluşturmanın programlı bir yolu yoktur. Bu nedenle, uygulamanız verileri bir Microsoft Access veri kaynağına (. mdb dosyası) yerleştirmenizi gerektiriyorsa, büyük olasılıkla her ihtiyaç duyduğunuzda kullanabileceğiniz veya kopyalayabileceğiniz boş bir. mdb dosyasına sahip olmak istersiniz.

Ancak, birçok DBMS programlı veri kaynağı oluşturmaya izin verir. Bazı veri kaynakları veritabanları için bir dizin belirtimi bulundurur. Diğer bir deyişle, bir dizin veri kaynağıdır ve veri kaynağı içindeki her tablo ayrı bir dosyada depolanır (dBASE durumunda her tablo bir. dbf dosyasıdır). Microsoft Access ve SQL Server gibi diğer ODBC veritabanlarına yönelik Sürücüler, bir veri kaynağı oluşturulmadan önce bazı belirli ölçütlerin karşılanmasını gerektirir. Örneğin, SQL Server ODBC sürücüsünü kullanırken SQL Server bir bilgisayar oluşturmuş olmanız gerekir.

##  <a name="_core_sqlconfigdatasource_example"></a>SQLConfigDataSource örneği

Aşağıdaki örnek, yeni Excel veri kaynağı adlı yeni bir Excel veri kaynağı oluşturmak için `::SQLConfigDataSource` ODBC API işlevini kullanır:

```
SQLConfigDataSource(NULL,ODBC_ADD_DSN, "Excel Files (*.xls)",
                   "DSN=New Excel Data Source\0"
                   "Description=New Excel Data Source\0"
                   "FileType=Excel\0"
                   "DataDirectory=C:\\EXCELDIR\0"
                   "MaxScanRows=20\0");
```

Veri kaynağının gerçekten bir dizin (C:\EXCELDIR) olduğunu unutmayın; Bu dizin mevcut olmalıdır. Excel sürücüsü, dizinleri veri kaynakları ve dosyalar olarak (. xls dosyası başına tek tablo) kullanır.

Tablo oluşturma hakkında daha fazla bilgi için bkz. [veri kaynağı: program aracılığıyla ODBC veri kaynağında tablo oluşturma](../../data/odbc/data-source-programmatically-creating-a-table-in-an-odbc-data-source.md).

Aşağıdaki bilgiler `::SQLConfigDataSource` ODBC API işlevine geçirilmesi gereken parametreleri açıklar. `::SQLConfigDataSource`kullanmak için Odbcinst. h üstbilgi dosyasını dahil etmeniz ve Odbcinst. lib içeri aktarma kitaplığını kullanmanız gerekir. Ayrıca, Odbccp32. dll dosyasının çalışma zamanında yolunda olması gerekir (veya 16 bit için Odbcinst. dll).

ODBC Yöneticisi 'ni veya benzer bir yardımcı programı kullanarak bir ODBC veri kaynağı adı oluşturabilirsiniz. Ancak bazen, kullanıcının ayrı bir yardımcı program çalıştırmasını gerektirmeden erişim sağlamak için doğrudan uygulamanızdan bir veri kaynağı adı oluşturulması istenebilir.

ODBC Yöneticisi (genellikle Denetim Masası 'nda yüklü), girdileri Windows kayıt defterine (veya 16 bit için ODBC. ini dosyasına) yerleştirerek yeni bir veri kaynağı oluşturur. ODBC Sürücü Yöneticisi, veri kaynağı hakkında gerekli bilgileri almak için bu dosyayı sorgular. `::SQLConfigDataSource`çağrısıyla birlikte sağlamanız gerektiğinden, kayıt defterine hangi bilgilerin yerleştirilmesi gerektiğini bilmeniz önemlidir.

Bu bilgiler `::SQLConfigDataSource`kullanılmadan doğrudan kayıt defterine yazılabilse de, bunu yapan tüm uygulamalar sürücü yöneticisinin verilerini korumak için kullandığı geçerli tekniğin üzerine bağlıdır. ODBC Sürücü Yöneticisi 'nin sonraki bir düzeltmesi farklı bir şekilde veri kaynakları ile ilgili kayıt tutmayı uygularsa, bu tekniği kullanan tüm uygulamalar bozulur. Genellikle bir API işlevi sağlandığında kullanılması önerilir. Örneğin, işlev doğru şekilde ODBC. ini dosyasına veya kayıt defterine yazdığı için `::SQLConfigDataSource` işlevini kullanırsanız, kodunuz 16 bitten 32 bite taşınabilir.

##  <a name="_core_sqlconfigdatasource_parameters"></a>SQLConfigDataSource parametreleri

Aşağıdaki `::SQLConfigDataSource` işlevinin parametrelerini açıklar. Bilgilerin çoğu, Visual C++ sürüm 1,5 ve üzeri Ile sağlanan ODBC API *Programmer 's başvurusundan* alınmıştır.

###  <a name="_core_function_prototype"></a>İşlev prototipi

```
BOOL SQLConfigDataSource(HWND hwndParent,UINT fRequest, LPCSTR lpszDriver, LPCSTR lpszAttributes);
```

### <a name="remarks"></a>Açıklamalar

####  <a name="_core_parameters_and_usage"></a>Parametreler ve kullanım

*hwndParent*<br/>
ODBC Sürücü Yöneticisi 'nin veya belirli ODBC sürücüsünün Kullanıcı tarafından yeni veri kaynağı hakkında ek bilgi almak için oluşturduğu herhangi bir iletişim kutusunun sahibi olarak belirtilen pencere. *LpszAttributes* parametresi yeterli bilgi sağlamamıyorsa bir iletişim kutusu görüntülenir. *HwndParent* parametresi null olabilir.

*IpszDriver*<br/>
Sürücü açıklaması. Bu, kullanıcılara fiziksel sürücü adı (DLL) yerine sunulan addır.

*lpszAttributes*<br/>
"KeyName = value" biçimindeki özniteliklerin listesi. Bu dizeler, listenin sonunda art arda iki null sonlandırıcıya sahip null sonlandırıcılar tarafından ayrılır. Bu öznitelikler, birincil olarak yeni veri kaynağı için kayıt defterine gidecek, sürücüye özgü varsayılan girişlerdir. Bu işlev için ODBC API başvurusunda belirtilmeyen önemli bir anahtar, yeni veri kaynağının adını belirten "DSN" ("veri kaynağı adı") ' dir. Girdilerin geri kalanı yeni veri kaynağı için sürücüye özeldir. Sürücü, kullanıcıdan yeni değerler için iletişim kutusuyla karşılaşabileceğinden, tüm girişleri sağlamak gerekli değildir. (Bunu yapmak için *hwndParent* değerini null olarak ayarlayın.) Kullanıcıya sorulmaması için varsayılan değerleri açıkça sağlamak isteyebilirsiniz.

#### <a name="to-determine-the-description-of-a-driver-for-the-lpszdriver-parameter-using-odbc-administrator"></a>ODBC Yöneticisi 'ni kullanarak IpszDriver parametresi için bir sürücünün açıklamasını belirleme

1. ODBC Yöneticisi 'ni çalıştırın.

1. **Ekle**'ye tıklayın.

Bu, yüklü sürücülerin ve açıklamalarının bir listesini sağlar. Bu açıklamayı *IpszDriver* parametresi olarak kullanın. Açıklamasında varsa dosya adı uzantısı ve parantez dahil olmak üzere, açıklamanın tamamını ("Excel Files (*. xls)" gibi) kullanacağınızı unutmayın.

Alternatif olarak, "ODBC sürücüleri" kayıt defteri anahtarı (veya Odbcinst. ini içindeki [ODBC Drivers] bölümü) altındaki tüm sürücü girişlerinin ve açıklamalarının listesini içeren kayıt defterini (veya 16 bit için Odbcinst. ini dosyasını) inceleyebilirsiniz.

*LpszAttributes* parametresi için bulmanın ve değerlerini bulmanın bir yolu, önceden yapılandırılmış bir veri kaynağı için ODBC. ini dosyasını incelemektir (belkı de ODBC Yöneticisi tarafından yapılandırılmış bir şekilde yapılandırılmıştır).

#### <a name="to-find-keynames-and-values-for-the-lpszattributes-parameter"></a>LpszAttributes parametresinin bulmanın ve değerlerini bulmak için

1. Windows kayıt defteri Düzenleyicisi 'ni çalıştırın (veya 16 bit için ODBC. ini dosyasını açın).

1. Aşağıdakilerden birini kullanarak ODBC veri kaynakları bilgilerini bulun:

   - 32 bit için, **\Software\odbc\odbcHKEY_CURRENT_USER anahtarını bulun. Sol bölmedeki ıNK\ODBC veri kaynakları** .

      Sağ bölmede, *\<veri kaynağı adı >* , kullanmayı düşündüğünüz sürücü için istenen ayarlarla yapılandırılmış bir veri kaynağı olan "pub: REG_SZ: *\<veri kaynağı adı >* " biçiminde girişler listelenmiştir. İstediğiniz veri kaynağını seçin, örneğin SQL Server. "Pub:" dizesini izleyen öğeler sırasıyla, *lpszAttributes* parametresinde kullanılacak KeyName ve değer olarak kullanılır.

   - 16 bit için, ODBC. ini dosyasında [ *\<veri kaynağı adı >* ] tarafından işaretlenen bölümü bulun.

      Bu satırı izleyen satırlar "KeyName = value" formundadır. Bunlar tam olarak, *lpszAttributes* parametrinizdeki kullanılacak girişlerdir.

Ayrıca, kullanacağınız belirli bir sürücünün belgelerini incelemek isteyebilirsiniz. ODBC Yöneticisi 'ni çalıştırarak erişebileceğiniz sürücü için çevrimiçi yardım 'da yararlı bilgiler bulabilirsiniz. Bu yardım dosyaları, genellikle Windows NT, Windows 3,1 veya Windows 95 için WINDOWS\SYSTEM dizinine yerleştirilir.

#### <a name="to-obtain-online-help-for-your-odbc-driver"></a>ODBC sürücünüze yönelik çevrimiçi yardım almak için

1. ODBC Yöneticisi 'ni çalıştırın.

1. **Ekle**'ye tıklayın.

1. Sürücü adını seçin.

1. **Tamam** düğmesine tıklayın.

ODBC Yöneticisi belirli bir sürücü için yeni bir veri kaynağı oluşturma bilgilerini görüntülediğinde **Yardım**' a tıklayın. Bu, genellikle sürücünün kullanımıyla ilgili önemli bilgileri içeren söz konusu sürücü için yardım dosyasını açar.

## <a name="see-also"></a>Ayrıca bkz.

[Veri Kaynağı (ODBC)](../../data/odbc/data-source-odbc.md)

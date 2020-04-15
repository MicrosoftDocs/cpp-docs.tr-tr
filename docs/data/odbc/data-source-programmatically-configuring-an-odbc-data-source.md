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
ms.openlocfilehash: ba0224d166795b34d636ace610265e115209e49c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358868"
---
# <a name="data-source-programmatically-configuring-an-odbc-data-source"></a>Veri Kaynağı: Program Aracılığıyla ODBC Veri Kaynağını Yapılandırma

Bu konu, Açık Veritabanı Bağlantısı (ODBC) veri kaynağı adlarını programlı olarak nasıl yapılandırabileceğinizi açıklar. Bu, kullanıcıyı veri kaynaklarının adlarını belirtmek için ODBC Yöneticisi'ni veya diğer programları açıkça kullanmaya zorlamadan verilere erişme esnekliği sağlar.

Genellikle, ilişkili veritabanı yönetim sistemi (DBMS) bu işlemi destekliyorsa, bir veri kaynağı oluşturmak için bir kullanıcı ODBC Administrator çalışır.

ODBC Administrator aracılığıyla bir Microsoft Access ODBC veri kaynağı oluştururken, size iki seçenek verilir: varolan bir .mdb dosyayı seçebilir veya yeni bir .mdb dosyası oluşturabilirsiniz. MFC ODBC uygulamanızdan .mdb dosyasını oluşturmanın programlı bir yolu yoktur. Bu nedenle, uygulamanız verileri bir Microsoft Access veri kaynağına (.mdb dosyası) yerleştirmenizi gerektiriyorsa, büyük olasılıkla ihtiyacınız olduğunda kullanabileceğiniz veya kopyalayabildiğiniz boş bir .mdb dosyasına sahip olmak istersiniz.

Ancak, birçok DBMSs programlı veri kaynağı oluşturma sağlar. Bazı veri kaynakları veritabanları için bir dizin belirtimi tutar. Diğer bir deyişle, dizin veri kaynağıdır ve veri kaynağıiçindeki her tablo ayrı bir dosyada depolanır (dBASE durumunda, her tablo bir .dbf dosyasıdır). Microsoft Access ve SQL Server gibi diğer ODBC veritabanlarının sürücüleri, bir veri kaynağı oluşturulmadan önce bazı belirli ölçütlerin karşılanmasını gerektirir. Örneğin, SQL Server ODBC sürücüsünü kullanırken bir SQL Server bilgisayarı oluşturmuş olmanız gerekir.

## <a name="sqlconfigdatasource-example"></a><a name="_core_sqlconfigdatasource_example"></a>SQLConfigDataSource Örneği

Aşağıdaki `::SQLConfigDataSource` örnekte, Yeni Excel Veri Kaynağı adı verilen yeni bir Excel veri kaynağı oluşturmak için ODBC API işlevini kullanır:

```
SQLConfigDataSource(NULL,ODBC_ADD_DSN, "Excel Files (*.xls)",
                   "DSN=New Excel Data Source\0"
                   "Description=New Excel Data Source\0"
                   "FileType=Excel\0"
                   "DataDirectory=C:\\EXCELDIR\0"
                   "MaxScanRows=20\0");
```

Veri kaynağının aslında bir dizin olduğunu unutmayın (C:\EXCELDIR); bu dizin var olmalıdır. Excel sürücüsü dizinleri veri kaynakları olarak kullanır ve dosyaları tek tek tablolar olarak (.xls dosyası başına bir tablo).

Tablo oluşturma hakkında daha fazla bilgi için [bkz: Veri Kaynağı: ODBC Veri Kaynağı'nda Programlı olarak Tablo Oluşturma.](../../data/odbc/data-source-programmatically-creating-a-table-in-an-odbc-data-source.md)

Aşağıdaki bilgiler, `::SQLConfigDataSource` ODBC API işlevine geçirilmesi gereken parametreleri tartışır. Kullanmak `::SQLConfigDataSource`için, Odbcinst.h başlık dosyasını eklemeniz ve Odbcinst.lib alma kitaplığını kullanmanız gerekir. Ayrıca, Odbccp32.dll çalışma zamanında yolda olmalıdır (veya 16 bit için Odbcinst.dll).

ODBC Administrator'ı veya benzer bir yardımcı programı kullanarak bir ODBC veri kaynağı adı oluşturabilirsiniz. Ancak, bazen kullanıcının ayrı bir yardımcı programı çalıştırmasını gerektirmeden erişim elde etmek için doğrudan uygulamanızdan bir veri kaynağı adı oluşturmak istenir.

ODBC Administrator (genellikle Denetim Masası'nda yüklü) Windows kayıt defterine girişleri koyarak yeni bir veri kaynağı oluşturur (veya 16 bit için Odbc.ini dosyasına). ODBC Sürücü Yöneticisi, veri kaynağı hakkında gerekli bilgileri almak için bu dosyayı sorgular. Kayıt defterine hangi bilgilerin konulması gerektiğini bilmek önemlidir, çünkü bunu `::SQLConfigDataSource`.

Bu bilgiler kullanmadan `::SQLConfigDataSource`doğrudan kayıt defterine yazılabilir, ancak bunu yapan herhangi bir uygulama, Sürücü Yöneticisi'nin verilerini korumak için kullandığı geçerli tekniğe dayanır. ODBC Sürücü Yöneticisi'nde daha sonra yapılan bir düzeltme, veri kaynakları hakkında farklı bir şekilde kayıt tutma uygularsa, bu tekniği kullanan herhangi bir uygulama bozulur. Genellikle bir API işlevi sağlandığında kullanılması tavsiye edilir. Örneğin, `::SQLConfigDataSource` işlevi kullanırsanız kodunuz 16 bit ile 32 bit arasında taşınabilir, çünkü işlev Odbc.ini dosyasına veya kayıt defterine doğru şekilde yazar.

## <a name="sqlconfigdatasource-parameters"></a><a name="_core_sqlconfigdatasource_parameters"></a>SQLConfigDataSource Parametreleri

Aşağıdaki işlevin parametrelerini `::SQLConfigDataSource` açıklar. Bilgilerin çoğu Visual C++ sürüm 1.5 ve sonrası ile birlikte verilen ODBC API *Programcısı Referansından* alınmıştır.

### <a name="function-prototype"></a><a name="_core_function_prototype"></a>Fonksiyon Prototipi

```
BOOL SQLConfigDataSource(HWND hwndParent,UINT fRequest, LPCSTR lpszDriver, LPCSTR lpszAttributes);
```

### <a name="remarks"></a>Açıklamalar

#### <a name="parameters-and-usage"></a><a name="_core_parameters_and_usage"></a>Parametreler ve Kullanım

*hwndParent*<br/>
ODBC Sürücü Yöneticisi veya belirli ODBC sürücüsünün oluşturduğu iletişim kutularının sahibi olarak belirtilen pencere, kullanıcıdan yeni veri kaynağı hakkında ek bilgi almak için oluşturulur. *lpszAttributes* parametresi yeterli bilgi sağlanmazsa, bir iletişim kutusu görüntülenir. *hwndParent* parametresi NULL olabilir.

*lpszDriver*<br/>
Sürücü açıklaması. Bu, fiziksel sürücü adı (DLL) yerine kullanıcılara sunulan addır.

*lpszAttributes*<br/>
"Anahtar adı=değer" şeklindeki özniteliklerin listesi. Bu dizeleri listenin sonunda iki ardışık null sonlandırıcı ile null terminators tarafından ayrılır. Bu öznitelikler, öncelikle yeni veri kaynağı için kayıt defterine giden varsayılan sürücüye özgü girişlerdir. Bu işlev için ODBC API başvurusunda belirtilmeyen önemli bir anahtar, yeni veri kaynağının adını belirten "DSN" ("veri kaynağı adı") 'dır. Girişlerin geri kalanı yeni veri kaynağı için sürücüye özgüdür. Sürücü kullanıcıya yeni değerler için iletişim kutuları isteyebilir, çünkü genellikle tüm girişleri sağlamak için gerekli değildir. (Buna neden olması için *HWndParent'ı* NULL olarak ayarlayın.) Kullanıcıdan istenmemesi için varsayılan değerleri açıkça sağlamak isteyebilirsiniz.

#### <a name="to-determine-the-description-of-a-driver-for-the-lpszdriver-parameter-using-odbc-administrator"></a>ODBC Administrator kullanarak lpszDriver parametresi için bir sürücünün açıklamasını belirlemek için

1. ODBC Yöneticisi'ni çalıştırın.

1. **Ekle**’ye tıklayın.

Bu, yüklü sürücülerin ve açıklamalarının bir listesini verir. Bu açıklamayı *lpszDriver* parametresi olarak kullanın. "Excel Files (*.xls)" gibi tüm açıklamayı, dosya adı uzantısı ve eşlilikler de dahil olmak üzere açıklamanın tamamını kullandığınızı unutmayın.

Alternatif olarak, kayıt defterini (veya 16 bit için Odbcinst.ini dosyası) inceleyebilirsiniz ve kayıt defteri anahtarı "ODBC Drivers" (veya Odbcinst.ini'deki [ODBC Sürücüleri] bölümü altında tüm sürücü girişlerinin ve açıklamalarının bir listesini içerir.

*LPSZAttributes* parametresi için anahtar adlarını ve değerlerini bulmanın bir yolu, önceden yapılandırılmış bir veri kaynağı (belki de ODBC Administrator tarafından yapılandırılmış bir veri kaynağı) için Odbc.ini dosyasını incelemektir.

#### <a name="to-find-keynames-and-values-for-the-lpszattributes-parameter"></a>lpszAttributes parametresi için anahtar adlarını ve değerlerini bulmak için

1. Windows kayıt defteri düzenleyicisini çalıştırın (veya 16 bit karşılığında Odbc.ini dosyasını açın).

1. Aşağıdakilerden birini kullanarak ODBC veri kaynakları bilgilerini bulun:

   - 32 bit için **HKEY_CURRENT_USER\Software\ODBC\ODBC anahtarını bulun. INI\ODBC Veri Kaynakları** sol bölmede.

      Sağ bölmede formun girişleri listelenir: "pub: REG_SZ: * \<* *\<veri kaynak adı>", *veri kaynağı adı>zaten kullanmak istediğiniz sürücü için istenen ayarlarla yapılandırılmış bir veri kaynağıdır. Örneğin, istediğiniz veri kaynağını seçin. "pub:" dizesini izleyen öğeler, *sırayla, lpszAttributes* parametrenizde kullanılacak anahtar adı ve değerdir.

   - 16 bit için, Odbc.ini dosyasında [*\<veri kaynak adı>*] ile işaretlenmiş bölümü bulun.

      Bu satırı izleyen satırlar "keyname=value" biçimindedir. Bunlar tam olarak *lpszAttributes* parametrenizde kullanılacak girişlerdir.

Ayrıca, kullanacağınız belirli sürücünün belgelerini de incelemek isteyebilirsiniz. ODBC Administrator'ı çalıştırarak erişebileceğiniz sürücü için çevrimiçi Yardım'da yararlı bilgiler bulabilirsiniz. Bu Yardım dosyaları genellikle Windows NT, Windows 3.1 veya Windows 95 için WINDOWS\SYSTEM dizinine yerleştirilir.

#### <a name="to-obtain-online-help-for-your-odbc-driver"></a>ODBC sürücünüz için çevrimiçi Yardım almak için

1. ODBC Yöneticisi'ni çalıştırın.

1. **Ekle**’ye tıklayın.

1. Sürücü adını seçin.

1. **Tamam**'a tıklayın.

ODBC Yöneticisi, belirli bir sürücü için yeni bir veri kaynağı oluşturmak için bilgileri görüntülediğinde, **Yardım'ı**tıklatın. Bu, genellikle sürücünün kullanımına ilişkin önemli bilgiler içeren söz konusu sürücü için Yardım dosyasını açar.

## <a name="see-also"></a>Ayrıca bkz.

[Veri Kaynağı (ODBC)](../../data/odbc/data-source-odbc.md)

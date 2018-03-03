---
title: "Veri kaynağı: Program aracılığıyla ODBC veri kaynağını yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SQLConfigDataSource
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources, configuring
- SQLConfigDataSource method example
- ODBC connections, configuring
- configuring ODBC data sources
ms.assetid: b8cabe9b-9e12-4d73-ae36-7cb12dee3213
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ac5756452a8b1c2d5dbf2f27ac7d3e1a8b069ca2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="data-source-programmatically-configuring-an-odbc-data-source"></a>Veri Kaynağı: Program Aracılığıyla ODBC Veri Kaynağını Yapılandırma
Bu konuda, açık veritabanı bağlantısı (ODBC) veri kaynağı adları programlı olarak nasıl yapılandırabileceğiniz açıklanmaktadır. Bu size esneklik verilere erişmek için açıkça veri kaynakları adlarını belirtmek için ODBC Yöneticisi veya diğer programları kullanmak üzere kullanıcı zorlamadan sağlar.  
  
 Genellikle, bir kullanıcı bu işlemi ilişkili veritabanı yönetim sistemi (DBMS) destekliyorsa, bir veri kaynağı oluşturmak için ODBC Yöneticisi çalışır.  
  
 Bir Microsoft Access ODBC veri kaynağı ODBC Yöneticisi yoluyla oluştururken, iki seçenek sunulur: varolan bir .mdb dosyasını seçebilir veya yeni bir .mdb dosyası oluşturabilirsiniz. MFC ODBC uygulamanızdan .mdb dosyasını oluşturma programlı bir yolu yoktur. Uygulamanızı bir Microsoft Access veri kaynağına (.mdb dosyası) verilerinin yerleştirilmesi gerektiriyorsa, bu nedenle, büyük olasılıkla kullanın ya da ihtiyaç duyduğunuzda kopyalama bir boş .mdb dosyasının istiyorsanız.  
  
 Ancak, birçok DBMS programlı veri kaynağı oluşturulmasına izin verir. Bazı veri kaynakları veritabanları için dizin belirtimi korur. Diğer bir deyişle, veri kaynağı bir dizindir ve her tablo veri kaynağı içinde ayrı bir dosyada depolanır (dBASE söz konusu olduğunda, her bir .dbf dosyası tablodur). Microsoft Access ve SQL Server gibi diğer ODBC veritabanları için sürücüleri, bir veri kaynağı oluşturulmadan önce bazı belirli bir ölçüte karşılanması gerektirir. Örneğin, SQL Server ODBC sürücüsü kullanırken, bir SQL Server bilgisayarı oluşturulmuş gerekir.  
  
##  <a name="_core_sqlconfigdatasource_example"></a>SQLConfigDataSource örneği  
 Aşağıdaki örnek kullanır **:: SQLConfigDataSource** yeni bir Excel veri kaynağı oluşturmak için ODBC API işlevi adlı yeni bir Excel veri kaynağı:  
  
```  
SQLConfigDataSource(NULL,ODBC_ADD_DSN, "Excel Files (*.xls)",   
                   "DSN=New Excel Data Source\0"   
                   "Description=New Excel Data Source\0"   
                   "FileType=Excel\0"   
                   "DataDirectory=C:\\EXCELDIR\0"   
                   "MaxScanRows=20\0");  
```  
  
 Veri kaynağı dizin gerçekte (C:\EXCELDIR); olduğuna dikkat edin Bu dizin mevcut olması gerekir. Excel sürücüsü dizinler, tek tek tablolar (.xls dosya başına tek tablo) gibi veri kaynaklarının ve dosyaları kullanır.  
  
 Tablo oluşturma hakkında daha fazla bilgi için bkz: [veri kaynağı: program aracılığıyla ODBC veri kaynağını bir tablodaki'ı oluşturma](../../data/odbc/data-source-programmatically-creating-a-table-in-an-odbc-data-source.md).  
  
 Aşağıdaki bilgiler için geçirilmesi gereken parametreleri açıklar **:: SQLConfigDataSource** ODBC API işlevi. Kullanılacak **:: SQLConfigDataSource**, Odbcinst.h üst bilgi dosyasını dahil ve Odbcinst.lib içeri aktarma kitaplığını kullanmanız gerekir. Ayrıca, Odbccp32.dll çalışma süresi (veya 16 bit Odbcinst.dll) yolu olmalıdır.  
  
 ODBC Yöneticisi veya benzer bir yardımcı programını kullanarak bir ODBC veri kaynağı adı oluşturabilirsiniz. Ancak, bazen, bir veri kaynağı adı ayrı bir yardımcı programı çalıştırmak kullanıcının gerek kalmadan erişim elde etmek için doğrudan uygulamanızı oluşturmak için tercih edilir.  
  
 ODBC Yöneticisi (genellikle Denetim Masası'nda yüklü), Windows Kayıt Defteri'nde (veya 16 bit, Odbc.ini dosyasındaki) girişleri koyarak yeni bir veri kaynağı oluşturur. ODBC Sürücü Yöneticisi veri kaynağı hakkında gerekli bilgileri almak için bu dosyayı sorgular. Hangi bilgilerin çağrısıyla sağlamanız gerektiğinden kayıt defterinde yerleştirilmesi gerektiğini bilmek önemlidir **:: SQLConfigDataSource**.  
  
 Bu bilgiler olmadan doğrudan kayıt defterine yazılabilir rağmen **:: SQLConfigDataSource**, bunu yapan herhangi bir uygulama verilerini korumak için Sürücü Yöneticisi'ni kullandığı geçerli tekniğe bağlı. Bu tekniği kullanan herhangi bir uygulama, daha sonraki bir düzeltmesi, farklı bir şekilde veri kaynakları hakkında tutma ODBC sürücü yöneticisini uygular kaydı bozuk. Genellikle sağlandığında bir API işlevi kullanmanız önerilir. Örneğin, kullanırsanız, kodu 32 bit 16 bit taşınabilir **:: SQLConfigDataSource** işlevi Odbc.ini dosyasına veya kayıt defteri yazdığından işlev.  
  
##  <a name="_core_sqlconfigdatasource_parameters"></a>SQLConfigDataSource parametreleri  
 Aşağıdaki parametreleri açıklar **:: SQLConfigDataSource** işlevi. Bilgilerin büyük bölümünü ODBC API öğesinden alınan *Programcının Başvurusu* Visual C++ sürüm 1.5 ve sonrası ile sağlanan.  
  
###  <a name="_core_function_prototype"></a>İşlev prototipi  
  
```  
BOOL SQLConfigDataSource(HWND hwndParent,UINT fRequest, LPCSTR lpszDriver, LPCSTR lpszAttributes);  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
####  <a name="_core_parameters_and_usage"></a>Parametreleri ve kullanım  
 *hwndParent*  
 Kullanıcı yeni veri kaynağı ile ilgili ek bilgi almak için ODBC Sürücü Yöneticisi veya belirli bir ODBC sürücüsüne oluşturur herhangi bir iletişim kutusu sahibi olarak belirtilen penceresini açın. Varsa `lpszAttributes` parametresi yeterli bilgi sağlamıyorsa, bir iletişim kutusu görüntülenir. *HwndParent* parametresi olabilir **NULL**.  
  
 `lpszDriver`  
 Sürücü açıklaması. Bu fiziksel sürücü adı (DLL) yerine kullanıcılara gösterilen addır.  
  
 `lpszAttributes`  
 Form içinde öznitelik listesi "keyname = value". Bu dizeler, listenin sonuna iki ardışık null sonlandırıcılar ile null sonlandırıcılar tarafından ayrılır. Bu, yeni veri kaynağı için kayıt defterine Git öncelikle varsayılan sürücüye özgü girişlerini öznitelikleridir. Bu işlev için ODBC API Başvurusu belirtilmeyen önemli bir anahtar "yeni veri kaynağının adını belirten DSN" ("veri kaynağı adı"), ' dir. Girişlerin geri kalanı yeni veri kaynağı için sürücü özgüdür. Genellikle sürücü iletişim kutuları için yeni değerleri kullanıcıyla isteyebilir çünkü tüm girişleri sağlamak gerekli değildir. (Ayarlamak *hwndParent* için **NULL** bu neden olacak.) Böylece kullanıcıdan istekte bulunulmaz açıkça varsayılan değerlerini sağlamak isteyebilirsiniz.  
  
###### <a name="to-determine-the-description-of-a-driver-for-the-lpszdriver-parameter-using-odbc-administrator"></a>ODBC Yöneticisi'ni kullanarak IpszDriver parametresi için bir sürücü açıklaması belirlemek için  
  
1.  ODBC Yöneticisi çalıştırın.  
  
2.  **Ekle**'yi tıklatın.  
  
 Bu, yüklenen sürücülerin ve açıklamalarının listesini sağlar. Bu açıklama olarak kullanmak `lpszDriver` parametresi. Açıklamasında varsa dosya adı uzantısı ve parantezler dahil olmak üzere tüm Açıklama "Excel dosyaları (*.xls)" gibi kullandığını unutmayın.  
  
 Alternatif olarak, kayıt defteri inceleyebilirsiniz (veya 16 bit, Odbcinst.ini dosyasını), tüm sürücü girişlerini ve açıklamaları "ODBC sürücüleri" kayıt defteri anahtarı altındaki (veya bölümü [ODBC sürücüleri] bölümünde) listesini içerir.  
  
 Anahtar adlarını ve değerlerini bulmak için tek yönlü `lpszAttributes` parametredir bir zaten yapılandırılmış veri kaynağı (belki de bir ODBC Yöneticisi tarafından yapılandırılan) ilişkin Odbc.ini dosyasını incelemek için.  
  
###### <a name="to-find-keynames-and-values-for-the-lpszattributes-parameter"></a>Anahtar adlarını ve değerleri lpszAttributes parametresi için bulmak için  
  
1.  Windows Kayıt Defteri Düzenleyicisi'ni çalıştırın (veya 16 bit için Odbc.ini dosyasını açın).  
  
2.  Aşağıdakilerden birini kullanarak ODBC veri kaynakları bilgilerini bulabilirsiniz:  
  
    -   32 bit için anahtar Bul **HKEY_CURRENT_USER\Software\ODBC\ODBC. INI\ODBC veri kaynakları** sol bölmede.  
  
         Sağ bölmede form girişlerini listeler: "pub: REG_SZ:*<data source name>*", burada  *<data source name>*  zaten düşündüğünüz sürücü için istenen ayarları ile yapılandırılmış bir veri kaynağı kullanmak için. İstediğiniz veri kaynağını, örneğin, SQL Server seçin. Dize izleyen öğeler "pub:" sipariş, keyname ve değerini kullanmak için olan, `lpszAttributes` parametresi.  
  
    -   16 bit tarafından işaretlenen Odbc.ini dosyasındaki bölüm Bul [*\<veri kaynağı adı >*].  
  
         Bu satırı aşağıdaki satırları biçimidir "keyname = value". Bunlar kullanmak için tam olarak girişler, `lpszAttributes` parametresi.  
  
 Kullanacağınız belirli bir sürücüyü belgelerine incelemek isteyebilirsiniz. ODBC Yöneticisi çalıştırarak erişebilirsiniz sürücü için çevrimiçi Yardım'daki yararlı bilgiler bulabilirsiniz. Bu Yardım dosyaları genellikle Windows NT, Windows 3.1 veya Windows 95 WINDOWS\SYSTEM dizininde yer alır.  
  
###### <a name="to-obtain-online-help-for-your-odbc-driver"></a>ODBC sürücüsü için çevrimiçi Yardım almak için  
  
1.  ODBC Yöneticisi çalıştırın.  
  
2.  **Ekle**'yi tıklatın.  
  
3.  Sürücü adını seçin.  
  
4.  **Tamam**'ı tıklatın.  
  
 ODBC Yöneticisi, belirli bir sürücüyü için yeni bir veri kaynağı oluşturmak için bilgileri görüntülediğinde tıklayın **yardımcı**. Bu genellikle sürücünün kullanımı ile ilgili önemli bilgiler içerir, bu sürücünün Yardım dosyasını açar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri Kaynağı (ODBC)](../../data/odbc/data-source-odbc.md)
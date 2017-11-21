---
title: "TN055: MFC ODBC veritabanı sınıfı uygulamalarını MFC DAO sınıflarına geçirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.odbc
dev_langs: C++
helpviewer_keywords:
- DAO [MFC], migration
- TN055
- migration [MFC], ODBC database applications
- ODBC classes [MFC], DAO classes
- migrating ODBC database applications [MFC]
- porting database applications to DAO
- ODBC [MFC], DAO
- porting ODBC database applications to DAO
- migrating database applications [MFC]
ms.assetid: 0f858bd1-e168-4e2e-bcd1-8debd82856e4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bb9b4041f9c288b40a6efb1ef7978d323bad2fb4
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="tn055-migrating-mfc-odbc-database-class-applications-to-mfc-dao-classes"></a>TN055: MFC ODBC Veritabanı Sınıfı Uygulamalarını MFC DAO Sınıflarına Geçirme
> [!NOTE]
>  Visual C++ ortamı ve sihirbazları DAO (DAO sınıfları dahil edilmiştir ve bunları kullanmaya devam edebilirsiniz ancak) desteklemez. Microsoft, kullanmanızı önerir [OLE DB Şablonları](../data/oledb/ole-db-templates.md) veya [ODBC ve MFC](../data/odbc/odbc-and-mfc.md) yeni projeler için. Yalnızca var olan uygulamaları sürdürmek DAO kullanmanız gerekir.  
  
 **Genel bakış**  
  
 Çoğu durumda MFC'nin ODBC veritabanı sınıfları MFC'nin DAO veritabanı sınıfları için kullanan uygulamaları geçirmek istenebilir. Bu teknik Not MFC ODBC ve DAO sınıfları arasındaki farklar çoğunu ayrıntılarını kaydeder. Aklınızda farklarla ODBC sınıfları için MFC sınıfları isterseniz uygulamaları geçirmek aşırı zor olmamalıdır.  
  
 **ODBC'den DAO'ya neden geçirme**  
  
 Pek çok neden uygulamaları ODBC veritabanı sınıflardan DAO veritabanı sınıfları geçirmek isteyebileceğiniz ancak kararı mutlaka basit veya belirgin değil vardır. Göz önünde bulundurmanız gereken tek şey DAO tarafından kullanılan Microsoft Jet veritabanı altyapısı erişebileceği bir ODBC sürücüsü olan herhangi bir ODBC veri kaynağını okunur. ODBC veritabanı sınıflarını kullanma veya kendiniz ancak Microsoft Jet veritabanı altyapısı ODBC verileri okuyabilir doğrudan ODBC çağrı daha etkili olabilir.  
  
 ODBC/DAO kararı kolay bazı basit durumlarda. Örneğin, yalnızca (erişim biçimi, Excel biçiminde ve benzeri) bariz seçim DAO veritabanı sınıfları kullanmaktır doğrudan Microsoft Jet altyapısı okuyabilir biçimde verilere erişim gerektiğinde.  
  
 Bir sunucuda veya farklı sunucularda, çeşitli verileriniz varsa, daha karmaşık durumlarda ortaya çıkar. Bu durumda, ODBC veritabanı sınıfları veya DAO veritabanı sınıfları kullanmayı zor bir karardır. İsterseniz şeyler heterojen birleşimler (SQL Server ve Oracle gibi çoklu biçimlerde sunuculardan birleştirme verileri) beğendiniz mi sonra Microsoft Jet veritabanı altyapısı yerine, için ODBC veritabanı kullandıysanız gerekli iş yapmanızı zorlama birleştirme gerçekleştirir Sınıflar ya da çağrılan ODBC'yi doğrudan. Sürücü imleçler destekleyen bir ODBC sürücüsü kullanıyorsanız, en iyi seçimdir ODBC veritabanı sınıfları olabilir.  
  
 Özel gereksinimlerinizi verilen çeşitli yöntemlerle performansını test etmek için bazı örnek kod yazma isteyebilirsiniz seçimi karmaşık, olabilir. Bu teknik Not DAO veritabanı sınıfları için ODBC veritabanı sınıflardan geçirmeye karar yaptığınız varsayılmaktadır.  
  
 **ODBC veritabanı sınıfları ve MFC DAO veritabanı sınıfları arasındaki benzerlikler**  
  
 MFC ODBC sınıfları, özgün tasarım Microsoft Access ve Microsoft Visual Basic kullanımda olan DAO nesne modeli temel. Başka bir deyişle, tüm bu bölümünde listelenir ODBC ve DAO MFC sınıfları birçok ortak özellik vardır. Genel olarak, programlama modelleri aynıdır.  
  
 Birkaç benzerlikler vurgulamak için:  
  
-   ODBC ve DAO sınıfları temel alınan veritabanı yönetim sistemi (DBMS) kullanarak yönetme veritabanı nesnelerini sahiptir.  
  
-   Hem bu DBMS döndürülen sonuç kümesini temsil eden bir kayıt kümesi nesneleri sahiptir.  
  
-   DAO veritabanı ve kayıt kümesi nesneleri üyeleri ODBC sınıfları için neredeyse aynı olmalıdır.  
  
-   Her iki sınıfları kümeleriyle verileri almak için kodu bazı nesne ve üye adı değişiklikler dışında aynıdır. Değişiklikleri gerekir ancak genellikle bir kolay ad değişikliği ODBC sınıflardan DAO sınıflarına geçerken işlemidir.  
  
 Örneğin, verileri almak için yordam her iki modellerde oluşturmak ve veritabanı nesnesini açmak için oluşturmak ve bir kayıt kümesi nesnesi açın ve (Taşı) ancak bazı işlemi gerçekleştirilirken veri gidin.  
  
 **ODBC ve DAO MFC sınıfları arasındaki farklar**  
  
 DAO sınıfları daha fazla nesneleri ve daha zengin bir dizi yöntem içerir, ancak bu bölüm yalnızca benzer sınıfları ve işlevleri farklılıkları ayrıntılarını kaydeder.  
  
 Sınıflar arasındaki en belirgin farklılıklar benzer sınıflar ve genel işlevler için ad değişikliklerini olabilirsiniz. Aşağıdaki liste nesneleri, yöntemleri ve veritabanı sınıfları ile ilişkili genel işlevler ad değişiklikleri gösterir:  
  
|Sınıf veya işlevi|MFC DAO sınıflarını eşdeğeri|  
|-----------------------|-----------------------------------|  
|`CDatabase`|`CDaoDatabase`|  
|`CDatabase::ExecuteSQL`|`CDaoDatabase::Execute`|  
|`CRecordset`|`CDaoRecordset`|  
|`CRecordset::GetDefaultConnect`|`CDaoRecordset::GetDefaultDBName`|  
|`CFieldExchange`|`CDaoFieldExchange`|  
|`RFX_Bool`|`DFX_Bool`|  
|`RFX_Byte`|`DFX_Byte`|  
|`RFX_Int`|`DFX_Short`|  
|`RFX_Long`|`DFX_Long`|  
||`DFX_Currency`|  
|`RFX_Single`|`DFX_Single`|  
|`RFX_Double`|`DFX_Double`|  
|**RFX_Date\***|**DFX_Date** (`COleDateTime`-tabanlı)|  
|`RFX_Text`|`DFX_Text`|  
|`RFX_Binary`|`DFX_Binary`|  
|`RFX_LongBinary`|`DFX_LongBinary`|  
  
 \*`RFX_Date` İşlevi temel `CTime` ve **TIMESTAMP_STRUCT**.  
  
 Uygulamanızı etkiler ve birden çok basit bir ad değişiklik gerektiren önemli değişiklikler işlevine aşağıda listelenmiştir.  
  
-   Kayıt kümesi gibi şeyleri türü açın ve kayıt kümesi açın seçeneklerini belirtmek için kullanılan makroları ve sabitleri değiştirildi.  
  
     ODBC sınıfları MFC makroları aracılığıyla bu seçenekler tanımlamak için gerekli veya türleri numaralandırılır.  
  
     DAO sınıfları ile DAO üstbilgi dosyası (DBDAOINT. Bu seçeneklerinde tanımını sağlar. H). Bu nedenle kayıt kümesi türü numaralandırılmış bir üyesi olan `CRecordset`, ancak DAO ile bir sabit yerine değil. Örneğin kullanırsınız **anlık görüntü** türünü belirtirken `CRecordset` ODBC'de ancak **DB_OPEN_SNAPSHOT** türünü belirtirken `CDaoRecordset`.  
  
-   Varsayılan kayıt kümesi türü `CRecordset` olan **anlık görüntü** while için varsayılan kayıt kümesi türü `CDaoRecordset` olan **dynaset** (ODBC sınıf anlık görüntüler hakkında ek bir sorun için aşağıdaki nota bakın).  
  
-   ODBC `CRecordset` sınıfı bir salt iletme kayıt kümesi türü oluşturmak için bir seçenek vardır. İçinde `CDaoRecordset` sınıfı, salt iletme kayıt kümesi türü ancak bunun yerine bir özellik (veya seçeneği), belirli türde bir kayıt kümeleri değil.  
  
-   Açarken yalnızca append bir kayıt bir `CRecordset` nesne kümesinin veri okuma ve eklenmiş olduğunu anlamına gelir. İle `CDaoRecordset` nesnesi, yalnızca ekleme seçeneği olabileceği anlamına gelir tam anlamıyla kümesinin verileri yalnızca eklenen (ve okuma değil).  
  
-   ODBC sınıfları işlem üye işlevleri üyesi `CDatabase` ve veritabanı düzeyinde davranacak. DAO sınıfları işlem üye işlevleri, daha yüksek bir düzeyinde sınıf üyesi (`CDaoWorkspace`) ve böylece çoklu etkileyebilir `CDaoDatabase` nesneleri paylaşımı aynı çalışma (işlem alanı).  
  
-   Özel durum sınıfı değiştirildi. **CDBExceptions** ODBC sınıfları oluşturulur ve **CDaoExceptions** DAO sınıflardaki.  
  
-   `RFX_Date`kullanan `CTime` ve **TIMESTAMP_STRUCT** sırasında nesneleri **DFX_Date** kullanan `COleDateTime`. `COleDateTime` Hemen hemen aynıdır `CTime`, 8-bayt OLE üzerinde temel ancak **tarih** 4-bayt yerine `time_t` çok daha geniş bir yelpazede veri tutabilen şekilde.  
  
    > [!NOTE]
    >  DAO (`CDaoRecordset`) ODBC salt okunur anlık görüntüler (`CRecordset`) anlık görüntüleri sürücü ve ODBC imleç kitaplığı kullanımını bağlı olarak güncelleştirilebilir. İmleç kitaplığı kullanıyorsanız `CRecordset` anlık görüntüleri güncelleştirilebilir. ODBC imleç kitaplığı Microsoft sürücüleri Masaüstü Sürücü Paketi 3.0 kullanıyorsanız, `CRecordset` salt okunur anlık görüntüler. Başka bir sürücü kullanıyorsanız, olmadığını görmek için sürücünün belgelerine bakın anlık görüntüler (**STATIC_CURSORS**) salt okunurdur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)


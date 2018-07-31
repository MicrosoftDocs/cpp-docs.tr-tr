---
title: 'Kayıt kümesi: Veri sütunlarını (ODBC) dinamik olarak bağlama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets [C++], binding columns dynamically
- data binding [C++], recordset columns
- recordsets [C++], binding data
- data binding [C++], columns in recordsets
- columns [C++], binding to recordsets
ms.assetid: bff67254-d953-4ae4-9716-91c348cb840b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fe0be424b07fd9d13eec63c56172b2b0195b83d9
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338817"
---
# <a name="recordset-dynamically-binding-data-columns-odbc"></a>Kayıt Kümesi: Veri Sütunlarını Dinamik Olarak Bağlama (ODBC)
Bu konu MFC ODBC sınıflarına uygulanır.  
  
 Tasarım zamanında belirttiğiniz bağlama tablo sütunları kayıt kümelerini yönetme, ancak bazı durumlarda, tasarım zamanında bilinmeyen sütunları bağlamak isteyebilirsiniz. Bu konu şunları açıklar:  
  
-   [İsteyebileceğiniz sütunları dinamik olarak bir kayıt kümesine bağlamak](#_core_when_you_might_bind_columns_dynamically).  
  
-   [Sütunları dinamik olarak çalışma zamanında bağlamak nasıl](#_core_how_to_bind_columns_dynamically).  
  
> [!NOTE]
>  Bu konu, türetilmiş nesneler için geçerlidir. `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız genel olarak açıklanan olan tekniklerle önerilmez. Toplu satır getirme hakkında daha fazla bilgi için bkz. [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_when_you_might_bind_columns_dynamically"></a> Sütunları dinamik olarak bağladığınızda  
 Tasarım zamanında, MFC Uygulama Sihirbazı'nı veya [MFC ODBC Tüketicisi Sihirbazı](../../mfc/reference/adding-an-mfc-odbc-consumer.md) (gelen **sınıfı Ekle**) göre bilinen tablolar ve sütunlar, veri kaynağında kayıt kümesi sınıfları oluşturur. Veritabanları, bunları ve daha sonra uygulamanızın çalışma zamanında bu tablolar ve sütunlar kullandığında tasarlarken arasında değiştirebilirsiniz. Siz veya başka bir kullanıcı veya bir tablo bırakma eklediğinizde veya uygulamanızın kayıt dayanan bir tablodaki sütunları kaldırın. Bu büyük olasılıkla tüm veri erişim uygulamaları için önemli değildir, ancak sizin, nasıl, veritabanı şeması, yeniden derlemeden ve yeniden tasarlanmasını dışındaki değişikliklerle başa çıkabilir? Bu soruyu cevaplamak için bu konunun amacı olan.  
  
 Bu konu içinde bağlama sütunları dinamik olarak en sık karşılaşılan durum açıklar; bilinen veritabanı şemasını temel alan bir kayıt kümesi ile başlamış, çalışma zamanında ek sütunlar işlemek istediğiniz. Konusunda daha fazla ek sütunlar için harita varsayar `CString` alan veri üyeleri, en sık karşılaşılan durum ancak diğer veri türlerini yönetmenize yardımcı olacak öneriler sağlanır.  
  
 Ek bir kod az miktarda ile şunları yapabilirsiniz:  
  
-   [Çalışma zamanında hangi sütunların bulunduğunu belirlemek](#_core_how_to_bind_columns_dynamically).  
  
-   [Ek sütunları kümenize çalışma zamanında dinamik olarak bağlama](#_core_adding_the_columns).  
  
 Kümenizin hala tanıdığınız tasarım zamanında sütunlar için veri üyelerini içerir. Bu da az miktarda bir dinamik olarak yeni sütun, hedef tabloda eklenip eklenmediğini belirler. ek bir kod içerir ve bu durumda, bu yeni sütunlar dinamik olarak ayrılan depolama alanını (yerine kayıt veri üyelerinin) bağlar.  
  
 Bu konuda, bırakılan tablolar ve sütunlar gibi diğer dinamik bağlama durumlarda kapsamaz. Bu gibi durumlarda daha doğrudan ODBC API çağrıları kullanmanız gerekir. Bilgi için bkz: ODBC SDK *Programcının Başvurusu* MSDN Kitaplığı CD'sindeki.  
  
##  <a name="_core_how_to_bind_columns_dynamically"></a> Sütunları dinamik olarak bağlama  
 Sütunları dinamik olarak bağlamak için gereken biliyorsanız (veya saptayabilmeniz) ek sütunların adları. Ayrıca ek alan veri üyeleri için depolamanın ayrılmasıyla, adlarını ve türlerini belirtin ve eklemekte olduğunuz sütun sayısını belirtmeniz gerekir.  
  
 İki farklı kayıt kümeleri aşağıdaki tartışma değinmektedir. Hedef tablo kayıtlarını seçtiği ana kayıt davranıştır. Hedef tabloda sütunlar hakkında bilgi almak için kullanılan özel bir sütun kayıt saniyedir.  
  
###  <a name="_core_the_general_process"></a> Genel işlem  
 En genel düzeyde, aşağıdaki adımları izleyin:  
  
1.  Uygulamanızın ana kayıt kümesi nesnesi oluşturun.  
  
     İsteğe bağlı olarak, açık bir işaretçinin geçirin `CDatabase` nesne veya sütun kayıt kümesini başka bir şekilde bağlantı bilgilerini sağlamanız gerekir.  
  
2.  Sütunları dinamik olarak eklemek için adımları uygulayın.  
  
     Aşağıdaki sütunları ekleme açıklanan işlemi bakın.  
  
3.  Ana kayıt açın.  
  
     Kayıt kümesi kayıtları seçer ve hem statik sütunları (Bu kayıt alan veri üyeleri için eşlenen) hem de (ayırdığınız ek depolama alanına eşlenen) dinamik sütun bağlama için kayıt alanı değişimi (RFX) kullanır.  
  
###  <a name="_core_adding_the_columns"></a> Sütun ekleme  
 Dinamik olarak bağlama, çalışma zamanında sütun, aşağıdaki adımları gerektirir eklenir:  
  
1.  Çalışma zamanında, hedef tabloda sütun nelerdir belirleyin. Bu bilgileri, kayıt kümesi sınıfı tasarlandığından beri tabloya eklenen sütunları listesini ayıklayın.  
  
     Veri kaynağı için (örneğin, sütun adı ve veri türü) hedef tablosu için sütun bilgileri sorgulamak üzere tasarlanmış bir sütun kayıt sınıf kullanmak iyi bir yaklaşımdır.  
  
2.  Yeni alan veri üyeleri için depolama alanı sağlar. Alan veri üyeleri bilinmeyen sütunlar için ana kayıt sınıfınıza sahip olmadığından (sütunları farklı veri türleri ise) adları, sonuç değerlerini ve büyük olasılıkla veri türü bilgilerini depolamak için bir yer sağlamanız gerekir.  
  
     Bir yaklaşım bir veya daha fazla dinamik listeler bir yeni sütunların adları için başka bir sonuç değerleri, ve veri türleri için üçüncü (gerekirse) oluşturmaktır. Bu listeler, özellikle değer listesi, bilgi ve bağlama için gerekli depolama sağlar. Aşağıdaki şekil, liste oluşturmayı gösterir.  
     ![Sütunları dinamik olarak bağlama listeleri oluşturmaya](../../data/odbc/media/vc37w61.gif "vc37w61")  
Sütunları dinamik olarak bağlamak için yapı listesi  
  
3.  Ana kümenizin içinde bir RFX işlev çağrısı ekleyin `DoFieldExchange` eklenmiş her sütun için işlev. RFX çağrıları getirilirken bir kaydı, ek sütunlar içeren ve sütunlarını kayıt veri üyelerinin veya dinamik olarak sağlanan depolama alanınızın kendileri için bağlama işlemlerini yapın.  
  
     Bir yaklaşım ise ana kümenizin bir döngü eklemek için `DoFieldExchange` , listedeki her sütun için uygun RFX işlevi çağırmak, yeni bir sütun listesi üzerinden döngü işlevi. RFX her çağrıda, sütun adı listesi ve bir depolama konumuna karşılık gelen sonuç değeri listesi üyesi bir sütun adı geçirin.  
  
###  <a name="_core_lists_of_columns"></a> Sütun listesi  
 Çalışmak için gereken dört liste aşağıdaki tabloda gösterilmektedir.  
  
 **Geçerli tablo sütunlarını (çizimdeki liste 1)** şu anda veri kaynağı üzerinde tablodaki sütunlar listesi. Bu liste, şu anda kümenize bağlı sütun listesi eşleşebilir.  
  
 **Bağlı kayıt kümesi sütunları (çizimdeki Liste 2)**  
 Sütun listesini kümenize bağlı. Bu sütunlar zaten RFX deyimleri içerir, `DoFieldExchange` işlevi.  
  
 **Bağlama-dinamik sütunlar (çizimdeki liste 3)**  
 Sütun tablodaki ancak kayıt listesi. Dinamik olarak bağlamak istediğiniz sütunları şunlardır.  
  
 **Dinamik sütun değerleri (şekildeki listesi 4)**  
 Depolama için değerleri içeren bir liste sütunları dinamik olarak bağlama alınır. Bu liste öğeleri de bağlama-dinamik sütunlar, bire bir karşılık gelir.  
  
###  <a name="_core_building_your_lists"></a> Listelerinizi oluşturma  
 Göz önünde genel bir strateji ile ayrıntılara kapatabilirsiniz. Bu konunun geri kalanında yordamları gösterilen listeleri nasıl oluşturacağınızı göstermek [sütun listeleri](#_core_lists_of_columns). Yordamlarda size kılavuzluk eder:  
  
-   [Kümenizde bulunmayan sütunlarının adlarını belirleme](#_core_determining_which_table_columns_are_not_in_your_recordset).  
  
-   [Tabloya eklenen sütunları için dinamik depolama alanı sağlayarak](#_core_providing_storage_for_the_new_columns).  
  
-   [RFX dinamik olarak ekleme, yeni sütunlar için çağıran](#_core_adding_rfx_calls_to_bind_the_columns).  
  
###  <a name="_core_determining_which_table_columns_are_not_in_your_recordset"></a> Tablo sütunları bir işlem olan kümenizde olmadığını belirleme  
 Ana kümenize zaten bağlı sütun listesini içeren bir liste (bağlı kayıt kümesi sütunları, liste 2 çizimde olduğu gibi) oluşturun. Ardından veri kaynağında tablo ancak ana kümenizin sütun adları içeren bir liste (sütun-için-bağlama-geçerli tablo sütunları ve bağlı kayıt kümesi sütunları türetilmiş dinamik) oluşturun.  
  
##### <a name="to-determine-the-names-of-columns-not-in-the-recordset-columns-to-bind-dynamically"></a>Kayıt kümesi (dinamik bağlama sütunlar) içinde olmayan sütun adlarını belirlemek için  
  
1.  Ana kümenize zaten bağlı sütunları (bağlı kayıt kümesi sütunları) listesi oluşturun.  
  
     Bir yaklaşım, tasarım zamanında bağlı kayıt kümesi sütunları oluşturmaktır. Görsel olarak kümesinin RFX işlev çağrılarında inceleyebilirsiniz `DoFieldExchange` işlevi bu adları alınamadı. Ardından, listenize adlar ile başlatılan bir dizi olarak ayarlayın.  
  
     Örneğin, çizim üç öğeye bağlı kayıt kümesi sütunları (Liste 2) gösterir. Bağlı kayıt kümesi sütunları geçerli tablo sütunları içinde (liste 1) gösterilen Telefon sütunu eksik.  
  
2.  Geçerli tablo sütunları ve bağlı kayıt kümesi sütunları (dinamik bağlama sütunlar) henüz ana kümenize bağlı sütun listesini oluşturmak için karşılaştırın.  
  
     Çalışma zamanı (geçerli tablo sütunları) ve kümenize (bağlı kayıt kümesi sütunları) paralel olarak zaten bağlı sütun listesi tablosunda sütun listesi döngü bir yaklaşımdır. Bağlama-dinamik sütunlar herhangi bir adı geçerli tablo-bağlı-kayıt kümesi-sütunları görünmeyen sütunları yerleştirin.  
  
     Örneğin, çizim ile bir öğe-bağlama-dinamik sütunlar (liste 3) göstermektedir: Telefon sütunu Geçerli tablo sütunları (liste 1), ancak bağlı kayıt kümesi sütunları (Liste 2) içinde bulunamadı.  
  
3.  Sütunları dinamik olarak bağlama listenizde depolanan her sütun adına (dinamik bağlama sütunlar) karşılık gelen veri değerleri depolamak için sütun dinamik değerleri (olduğu gibi çizimdeki liste 4) listesi oluşturun.  
  
     Bu liste öğelerini, alan veri üyeleri yeni kümesinin bir rol oynar. Bunlar, dinamik sütunları bağlı depolama yerleridir. Listeleri açıklamaları için bkz. [sütun listeleri](#_core_lists_of_columns).  
  
###  <a name="_core_providing_storage_for_the_new_columns"></a> Yeni sütunlar için depolama sağlama  
 Ardından, sütunları dinamik olarak bağlanması için depolama konumlarını ayarlayın. Fikir, her bir sütunun değeri depolamak için bir liste öğesinin sağlamaktır. Bu depolama konumları, normalde bağlı sütun depolama kayıt kümesi üye değişkenleri paralel.  
  
##### <a name="to-provide-dynamic-storage-for-new-columns-dynamic-column-values"></a>Yeni sütunlar (sütun-Dynamic-Values) için dinamik depolama sağlamak için  
  
1.  Dinamik sütun değerleri, paralel sütunları-için-bağlama-her sütunda verinin değerinin içerecek şekilde dinamik olarak oluşturun.  
  
     Örneğin, dinamik sütun değerleri (liste 4) sahip bir öğe aşağıdaki gösterimde: bir `CString` geçerli kayda gerçek telefon numarası içeren bir nesne: "555-1212".  
  
     En yaygın durumda dinamik sütun değerleri türünde öğelere sahip `CString`. Sütunları farklı veri türleri ile uğraşıyorsanız, çeşitli türleri öğelerini içerebilir bir listesi gerekir.  
  
 Aşağıdaki yordamlardan iki ana liste sonucudur:-bağlama-adlarını sütun ve dinamik sütun geçerli kayda sütundaki değerleri içeren değerleri içeren dinamik sütunlar.  
  
> [!TIP]
>  Yeni sütunlar tümü aynı veri türünde değilse, ek bir paralel şekilde sütun listesinde karşılık gelen her öğe türünü tanımlayan içeren öğeleri listesinde isteyebilirsiniz. (Ve vb. için bu, kullanmak istediğiniz değerleri AFX_RFX_BOOL AFX_RFX_BYTE kullanabilirsiniz. Bu sabitler AFXDB içinde tanımlanır. H) Sütun veri türlerini nasıl temsil bağlı bir liste türünü seçin.  
  
###  <a name="_core_adding_rfx_calls_to_bind_the_columns"></a> Sütunları bağlamak için RFX çağrıları ekleme  
 Son olarak, yeni sütunlar için RFX çağrılarını yerleştirerek gerçekleşmesi dinamik bağlama için düzenleme, `DoFieldExchange` işlevi.  
  
##### <a name="to-dynamically-add-rfx-calls-for-new-columns"></a>RFX dinamik olarak eklemek için yeni sütunlar için çağırır.  
  
1.  Ana kümenizin içinde `DoFieldExchange` üye işlev, yeni sütunlar (dinamik bağlama sütunlar) listesi üzerinden döngüler kodunu ekleyin. Her döngüde-bağlama-dinamik sütunlar ve bir sonuç değeri dinamik sütun değerleri sütunu için sütun adı Al. Bu öğeleri bir RFX işlev çağrısı sütununun veri türüne uygun geçirin. Listeleri açıklamaları için bkz. [sütun listeleri](#_core_lists_of_columns).  
  
 Ortak durumda, içinde `RFX_Text` işlev çağrıları, ayıklamak `CString` -bağlama-dinamik sütunlar olduğu kodu, aşağıdaki satırları olduğu gibi listeler nesnelerinden bir `CStringList` adlı `m_listName` ve dinamik sütun değerleri bir `CStringList` adlı `m_listValue`:  
  
```cpp  
RFX_Text( pFX,   
            m_listName.GetNext( posName ),   
            m_listValue.GetNext( posValue ));  
```  
  
 RFX işlevleri hakkında daha fazla bilgi için bkz. [makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md) içinde *sınıf kitaplığı başvurusu*.  
  
> [!TIP]
>  Yeni sütun farklı veri türleri, switch deyimi döngünüzde her türü için uygun RFX işlevi çağırmak için kullanın.  
  
 Framework çağırdığında `DoFieldExchange` sırasında `Open` statik sütunları bu sütunları bağlamak için kayıt kümesi RFX çağrıları sütunları bağlamak için işlem. Daha sonra döngünüzü dinamik sütunlar için tekrar tekrar RFX işlevleri çağırır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: Büyük Veri Öğeleri ile Çalışma (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)
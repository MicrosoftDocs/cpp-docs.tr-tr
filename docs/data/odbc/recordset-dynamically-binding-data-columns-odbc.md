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
ms.openlocfilehash: 9fe71707de20ba02228039e5693cab9c9401d560
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093392"
---
# <a name="recordset-dynamically-binding-data-columns-odbc"></a>Kayıt Kümesi: Veri Sütunlarını Dinamik Olarak Bağlama (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Kayıt kümeleri tasarım zamanında belirttiğiniz bağlama tablosu sütunlarını yönetir, ancak bazı durumlarda, tasarım zamanında bilinmeyen sütunları bağlamak isteyebilirsiniz. Bu konuda açıklanmaktadır:  
  
-   [İstediğinizde bir kayıt kümesi sütunları dinamik olarak bağlamak](#_core_when_you_might_bind_columns_dynamically).  
  
-   [Sütunları çalışma zamanında dinamik olarak bağlamak nasıl](#_core_how_to_bind_columns_dynamically).  
  
> [!NOTE]
>  Bu konuda türetilen nesnelere uygulanır `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız, genellikle açıklanan teknikleri önerilmez. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_when_you_might_bind_columns_dynamically"></a> Sütunları dinamik olarak bağladığınızda  
 Tasarım zamanında, MFC Uygulama Sihirbazı'nı veya [MFC ODBC Tüketici Sihirbazı](../../mfc/reference/adding-an-mfc-odbc-consumer.md) (gelen **sınıfı Ekle**) bilinen tablolar ve sütunlar, veri kaynağında göre kayıt kümesi sınıfları oluşturur. Veritabanları, bunları ve uygulamanızı çalışma zamanında tabloları ve sütunları kullandığında sonraki tasarlarken arasında değiştirebilirsiniz. Siz veya başka bir kullanıcı veya bir tablo bırakma eklediğinizde veya uygulamanızın kayıt dayanan bir tablodan sütun bırakma. Bu büyük olasılıkla tüm veri erişimi uygulamaları için bir sorun değildir, ancak için sizinse, nasıl, veritabanı şemasını, yeniden ve yeniden derlenmesi dışındaki değişiklikler başa? Bu soruyu yanıtlamak için bu konunun amacı budur.  
  
 Bu konu içinde bağladığınız sütunları dinamik olarak en yaygın durumda açıklar — bilinen veritabanı şemasını temel alan bir kayıt kümesi ile başlamış, çalışma zamanında ek sütunları istiyor. Ek sütunlar için eşleme konusunda daha fazla varsayar `CString` diğer veri türleri yönetmenize yardımcı olacak öneriler sağlasa alan veri üyeleri, en yaygın durumda.  
  
 Ek kod az miktarda ile şunları yapabilirsiniz:  
  
-   [Çalışma zamanında hangi sütunların kullanılabilir olduğunu belirlemek](#_core_how_to_bind_columns_dynamically).  
  
-   [Ek sütunlar kümenize çalışma zamanında dinamik olarak bağlama](#_core_adding_the_columns).  
  
 Kümenizin hala biliyorduk tasarım zamanında sütun için veri üyelerini içerir. Ayrıca dinamik olarak yeni sütunlar, hedef tabloya eklenip eklenmediğini belirler ek kod az miktarda içerir ve, varsa, bu yeni sütunları dinamik olarak ayrılan depolama alanı (yerine kayıt kümesi veri üyeleri) bağlar.  
  
 Bu konu, bırakılan tablolar ve sütunlar gibi diğer dinamik bağlama durumlarını kapsamaz. Bu gibi durumlarda ODBC API çağrılarını doğrudan kullanmanız gerekir. Bilgi için bkz: ODBC SDK *Programcının Başvurusu* MSDN Kitaplığı CD'sindeki.  
  
##  <a name="_core_how_to_bind_columns_dynamically"></a> Sütunları dinamik olarak bağlamak nasıl  
 Sütunları dinamik olarak bağlamak için bilmeniz (veya gerekir saptayabilmelisiniz) ek sütunlarının adlarını. Ayrıca ek alan veri üyeleri için depolama alanı ayırmak, adlarını ve türlerini belirtin ve eklediğiniz sütun sayısını belirtmeniz gerekir.  
  
 Aşağıdaki tartışma iki farklı kayıt kümeleri tanımlamıştır. İlk hedef tablosundan kayıtları seçer ana kayıt kümesidir. Hedef tabloda sütunları hakkında bilgi almak için kullanılan özel bir sütun kayıt saniyedir.  
  
###  <a name="_core_the_general_process"></a> Genel işlem  
 En genel düzeyde, aşağıdaki adımları izleyin:  
  
1.  Ana kayıt kümesi nesnesi oluşturun.  
  
     İsteğe bağlı olarak, açık bir işaretçi geçirmek `CDatabase` nesne veya sütun kayıt başka bir şekilde bağlantı bilgilerini sağlamanız gerekir.  
  
2.  Sütunları dinamik olarak eklemek için adımları uygulayın.  
  
     Aşağıdaki sütunları ekleme kısmında açıklanan işleme bakın.  
  
3.  Ana kümenizin açın.  
  
     Kayıt kümesi kayıtları seçer ve kayıt alanı değişimi (RFX) (tahsis ek depolama alanı için eşlenen) dinamik sütun, statik sütunlar (olanlar kayıt kümesi alan veri üyeleri için eşlenen) bağlamak için kullanır.  
  
###  <a name="_core_adding_the_columns"></a> Sütunlar ekleme  
 Dinamik olarak bağlama sütunları çalışma zamanında aşağıdaki adımları gerektirir eklendi:  
  
1.  Çalışma zamanında hedef tabloda sütun nelerdir belirler. Bu bilgileri, kayıt kümesi sınıfınız tasarlandığından beri tabloya eklenen sütunlar listesi ayıklayın.  
  
     Veri kaynağı (örneğin, sütun adı ve veri türü) hedef tablosu için sütun bilgileri için sorgulamak üzere tasarlanmış bir sütun kayıt kümesi sınıfını kullanmak iyi bir yaklaşımdır.  
  
2.  Yeni alan veri üyeleri için depolama alanı sağlar. Ana kayıt kümesi sınıfınızda bilinmeyen sütunlar için alan veri üyeleri olmadığından (sütunları farklı veri türleri ise) adları, sonuç değerleri ve büyük olasılıkla veri türü bilgilerini depolamak için bir yer sağlamanız gerekir.  
  
     Bir veya daha fazla dinamik listeleri, yeni sütun adları için bir tane, başka bir sonuç değerleri, ve kendi veri türleri için üçüncü (gerekirse) oluşturmak için bir yaklaşım ise. Bu listeler, özellikle değer listesi bilgileri ve bağlama için gerekli depolama sağlar. Aşağıdaki şekil liste oluşturmayı gösterir.  
     ![Sütunları dinamik olarak bağlamak için listelerini oluşturma](../../data/odbc/media/vc37w61.gif "vc37w61")  
Sütunları dinamik olarak bağlamak için yapı listesi  
  
3.  Ana kümenizin içinde bir RFX işlev çağrısı ekleyin `DoFieldExchange` eklenmiş her sütun için işlev. Bu RFX çağrıları bir kaydı getirme, ek sütunları içeren ve sütunları kayıt kümesi veri üyelerine veya dinamik olarak sağlanan depolama alanınızın kendileri için bağlama işlemlerini yapın.  
  
     Bir yaklaşım ise bir döngü ana kümenizin eklemek için `DoFieldExchange` listesindeki her bir sütun için uygun RFX işlevini çağırma yeni sütun listesi ile döngü işlevi. Her RFX çağrıda bir sütun adı sütun adı listesi ve bir depolama konumuna karşılık gelen sonuç değeri listesi üyesi geçirin.  
  
###  <a name="_core_lists_of_columns"></a> Sütun listesi  
 Çalışmak için gereken dört liste aşağıdaki tabloda gösterilmiştir.  
  
 **Geçerli tablo sütunları (çizimde liste 1)** şu anda veri kaynağı üzerinde tablodaki sütunlar listesi. Bu liste, şu anda kümenize bağlı sütunlar listesi eşleşebilir.  
  
 **Bağlı kayıt kümesi sütunları (çizimde Liste 2)**  
 Sütun listesini kümenize bağlı. Bu sütun zaten RFX deyimleri içerir, `DoFieldExchange` işlevi.  
  
 **BIND-dinamik sütunlar (çizimde liste 3)**  
 Tabloda yer alan ancak kümeniz sütun listesi. Dinamik olarak bağlamak istediğiniz sütunları bunlar.  
  
 **Dinamik sütun değerleri (çizimde liste 4)**  
 Depolama değerleri içeren bir liste dinamik olarak bağlama sütunlarından aldı. Bu liste öğeleri-BIND-dinamik sütunlar, bire bir de karşılık gelir.  
  
###  <a name="_core_building_your_lists"></a> Listelerinizi oluşturma  
 Genel bir strateji ile unutmayın, ayrıntılara kapatabilirsiniz. Bu konunun geri kalanında yordamlarda gösterilen listeleri nasıl oluşturacağınızı göstermek [sütun listeleri](#_core_lists_of_columns). Yordamlar size kılavuzluk eder:  
  
-   [Kümenizde bulunmayan sütunlarının adlarını belirleme](#_core_determining_which_table_columns_are_not_in_your_recordset).  
  
-   [Yeni tabloya eklenen sütunlar için dinamik depolama sağlama](#_core_providing_storage_for_the_new_columns).  
  
-   [RFX dinamik olarak ekleme çağırır yeni sütunlar için](#_core_adding_rfx_calls_to_bind_the_columns).  
  
###  <a name="_core_determining_which_table_columns_are_not_in_your_recordset"></a> Hangi tablo sütunları olan kümenizde olmadığını belirleme  
 Ana kümenize zaten bağlı sütun listesini içeren bir liste (bağlı kayıt kümesi sütunları, liste 2 çizimde olduğu gibi) oluşturun. Ardından veri kaynağında tablo, ancak ana kümenizde bulunmayan sütun adlarını içeren bir liste (-BIND-geçerli tablo sütunları ve bağlı kayıt kümesi sütunları türetilmiş dinamik sütunlar,) oluşturun.  
  
##### <a name="to-determine-the-names-of-columns-not-in-the-recordset-columns-to-bind-dynamically"></a>Sütun kümesinde bulunmayan (dinamik bağlama sütunlar) adlarını belirlemek için  
  
1.  Ana kümenize zaten bağlı sütunlar (bağlı kayıt kümesi sütunları) listesini oluşturun.  
  
     Bir yaklaşım, tasarım zamanında bağlı kayıt kümesi sütunları oluşturmaktır. Kayıt kümesinin RFX işlev çağrılarını görsel olarak inceleyebilirsiniz `DoFieldExchange` bu adları almak için işlevi. Ardından, listenizi adlar ile başlatılan bir dizi olarak ayarlayın.  
  
     Örneğin, çizim üç öğeye sahip bağlı kayıt kümesi sütunları (Liste 2) gösterir. Geçerli tablo sütunları içinde (liste 1) gösterilen Telefon sütunu bağlı kayıt kümesi sütunları eksik.  
  
2.  Geçerli tablo sütunları ve bağlı kayıt kümesi sütunları (dinamik bağlama sütunlar) ana kümenize zaten bağlı sütunlar listesi oluşturmak için karşılaştırın.  
  
     Çalışma zamanı (geçerli tablo sütunları) ve paralel olarak kümenize (bağlı kayıt kümesi sütunları) zaten bağlı sütunlar listesi tablodaki sütunlar listesi döngü bir yaklaşımdır. Geçerli tablo bağlı-kayıt-sütunları görünmeyen sütunları herhangi bir ad-BIND-dinamik sütunlar koyun.  
  
     Örneğin, şekil bir öğesiyle-BIND-dinamik sütunlar (liste 3) göstermektedir: Telefon sütunu Geçerli tablo sütunları (liste 1) ancak bağlı kayıt kümesi sütunları (Liste 2) bulunamadı.  
  
3.  Sütunları dinamik olarak bağlamak için listenizde depolanan her sütun adına (dinamik bağlama sütunlar) karşılık gelen veri değerleri depolanacağı sütun dinamik değerleri (örneğin, çizimdeki liste 4) listesini oluşturun.  
  
     Bu liste öğelerini, alan veri üyeleri yeni kayıt kümesi rol oynar. Dinamik sütun bağlı olan depolama konumları oldukları. Listeler açıklamaları için bkz: [sütun listeleri](#_core_lists_of_columns).  
  
###  <a name="_core_providing_storage_for_the_new_columns"></a> Yeni sütunlar için depolama sağlama  
 Ardından, dinamik olarak bağlı sütunlar için depolama konumları ayarlayın. Fikir her sütunun değeri depolanacağı bir liste öğesi sağlamaktır. Bu depolama konumları normal ilişkili sütunlara depolayan kayıt kümesi üye değişkenlerine paralel.  
  
##### <a name="to-provide-dynamic-storage-for-new-columns-dynamic-column-values"></a>Yeni sütunlar (dinamik sütun değerleri) için dinamik depolama alanı sağlamak için  
  
1.  Dinamik sütun değerleri, Paralel sütunlar-için-BIND-her sütunun veri değeri içerecek şekilde dinamik olarak oluşturun.  
  
     Örneğin, Şekil dinamik sütun değerlerini (liste 4) bir öğesiyle göstermektedir: bir `CString` geçerli kayıt için gerçek telefon numarasını içeren bir nesne: "555-1212".  
  
     En yaygın durumda dinamik sütun değerlerine sahip türündeki öğeler `CString`. Sütunları farklı veri türleri ile çalışıyorsanız, türleri çeşitli öğeleri içeren bir liste gerekir.  
  
 Aşağıdaki yordamlardan sonucunu iki ana listedir:-BIND-sütunlar ve dinamik-sütun-geçerli kayıt için sütundaki değerleri içeren bir değer adlarını içeren dinamik sütunlar.  
  
> [!TIP]
>  Yeni sütunlar aynı veri türünde tümünün emin değilseniz, fazladan bir paralel şekilde sütun listesinde karşılık gelen her öğe türünü tanımlar içeren öğeleri listesinde isteyebilirsiniz. (Değerleri kullanabilirsiniz **AFX_RFX_BOOL**, **AFX_RFX_BYTE**ve benzeri bu için istiyorsanız. Bu sabitleri AFXDB içinde tanımlanmıştır. H.) Veri türleri sütununu nasıl temsil göre bir liste türü seçin.  
  
###  <a name="_core_adding_rfx_calls_to_bind_the_columns"></a> Sütunları bağlamak için RFX çağrıları ekleme  
 Son olarak, yeni sütunlar için RFX çağrılarını yerleştirerek gerçekleşmesi dinamik bağlama için düzenleme, `DoFieldExchange` işlevi.  
  
##### <a name="to-dynamically-add-rfx-calls-for-new-columns"></a>RFX çağrıları yeni sütunlar için dinamik olarak eklemek için  
  
1.  Ana kümenizin içinde `DoFieldExchange` üye işlev, yeni sütunlar (dinamik bağlama sütunlar) listenize döngü kodu ekleyin. Her bir döngüde-BIND-dinamik sütunlar ve bir sonuç değeri dinamik sütun değerlerini sütunu için sütun adı Al. Bu öğeler bir RFX işlev çağrısı için sütunun veri türü için uygun geçirin. Listeler açıklamaları için bkz: [sütun listeleri](#_core_lists_of_columns).  
  
 Ortak durumda içinde `RFX_Text` işlev çağrıları, ayıklamak `CString` listelerden aşağıdaki satırları olduğu için bağ-dinamik sütunlar kodunun olduğu gibi nesneleri bir `CStringList` adlı `m_listName` ve dinamik sütun değerleri bir `CStringList` adlı `m_listValue`:  
  
```  
RFX_Text( pFX,   
            m_listName.GetNext( posName ),   
            m_listValue.GetNext( posValue ));  
```  
  
 RFX işlevleri hakkında daha fazla bilgi için bkz: [makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md) içinde *sınıf kitaplığı başvurusu*.  
  
> [!TIP]
>  Switch deyimi döngünüzde yeni sütunlar farklı veri türleri varsa, her türü için uygun RFX işlevi çağırmak için kullanın.  
  
 Framework çağırdığında `DoFieldExchange` sırasında **açık** statik sütunları bu sütunları bağlamak için sütunları kayıt kümesi RFX çağrılarının bağlamak için işlem. Daha sonra döngü dinamik sütunlar için RFX işlevleri art arda çağırır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: Büyük Veri Öğeleri ile Çalışma (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)
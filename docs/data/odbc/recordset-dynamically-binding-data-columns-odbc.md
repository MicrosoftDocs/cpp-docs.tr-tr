---
title: 'Kayıt Kümesi: Veri Sütunlarını Dinamik Olarak Bağlama (ODBC)'
ms.date: 05/09/2019
helpviewer_keywords:
- ODBC recordsets [C++], binding columns dynamically
- data binding [C++], recordset columns
- recordsets [C++], binding data
- data binding [C++], columns in recordsets
- columns [C++], binding to recordsets
ms.assetid: bff67254-d953-4ae4-9716-91c348cb840b
ms.openlocfilehash: f00fb92726cc37fe2bb0e95dc36e5fc1b6df201d
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86403874"
---
# <a name="recordset-dynamically-binding-data-columns-odbc"></a>Kayıt Kümesi: Veri Sütunlarını Dinamik Olarak Bağlama (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Kayıt kümeleri tasarım zamanında belirttiğiniz bağlama tablosu sütunlarını yönetir, ancak tasarım zamanında sizin için bilinmeyen sütunları bağlamak isteyebileceğiniz durumlar vardır. Bu konuda aşağıdakiler açıklanmaktadır:

- [Sütunları dinamik olarak bir kayıt kümesine bağlamak](#_core_when_you_might_bind_columns_dynamically)isteyebilirsiniz.

- [Sütunları çalışma zamanında dinamik olarak bağlama](#_core_how_to_bind_columns_dynamically).

> [!NOTE]
> Bu konu, `CRecordset` toplu satır yakalamanın uygulanmadığı, öğesinden türetilmiş nesneler için geçerlidir. Toplu satır getirme kullanıyorsanız, genel olarak açıklanan tekniklerin kullanılması önerilmez. Toplu satır getirme hakkında daha fazla bilgi için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="when-you-might-bind-columns-dynamically"></a><a name="_core_when_you_might_bind_columns_dynamically"></a>Sütunları dinamik olarak bağladığınızda

> [!NOTE]
> MFC ODBC Tüketicisi Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. Yine de bir tüketicisi el ile oluşturabilirsiniz.

Tasarım zamanında, MFC Uygulama Sihirbazı veya [MFC ODBC Tüketicisi Sihirbazı](../../mfc/reference/adding-an-mfc-odbc-consumer.md) ( **Sınıf Ekle**), veri kaynağınızdaki bilinen tabloları ve sütunları temel alan kayıt kümesi sınıfları oluşturur. Veritabanları, tasarım sırasında ve daha sonra uygulamanız bu tabloları ve sütunları çalışma zamanında kullandığında arasında değişebilir. Siz veya başka bir Kullanıcı bir tablo ekleyip bırakabilir veya uygulamanızın kayıt kümenizin bağımlı olduğu bir tabloya sütun ekleyebilir veya bırakabilirsiniz. Bu muhtemelen tüm veri erişimi uygulamaları için bir sorun değildir, ancak sizin için ise, yeniden tasarlama ve yeniden derleyerek, veritabanı şemasındaki değişikliklerle nasıl eğirsiniz? Bu konunun amacı, söz konusu soruyu yanıtlamak için kullanılır.

Bu konu başlığı altında, sütunları dinamik olarak bağlayabildiğiniz en yaygın durum açıklanmaktadır. bilinen bir veritabanı şemasına dayalı bir kayıt kümesiyle çalışmaya başladık, çalışma zamanında ek sütunları işlemek isteyebilirsiniz. Konu başlığı altında, `CString` diğer veri türlerini yönetmenize yardımcı olmak için öneriler sağlansa da, ek sütunların alan veri üyeleriyle, en yaygın olarak eşlenildiği varsayılmaktadır.

Az miktarda ek kodla şunları yapabilirsiniz:

- [Çalışma zamanında hangi sütunların kullanılabilir olduğunu belirleme](#_core_how_to_bind_columns_dynamically).

- [Çalışma zamanında kayıt kümenize dinamik olarak ek sütunlar bağlayın](#_core_adding_the_columns).

Kayıt kümeniz, tasarım zamanında bildiğimiz sütunların veri üyelerini hala içerir. Ayrıca, hedef tablonuza herhangi bir yeni sütun eklenip eklenmeyeceğini dinamik olarak belirleyen az miktarda ek kod içerir ve varsa, bu yeni sütunları dinamik olarak ayrılan depolama alanına (kayıt kümesi veri üyeleri yerine) bağlar.

Bu konu, bırakılan tablolar veya sütunlar gibi diğer dinamik bağlama durumlarını kapsamaz. Bu gibi durumlarda, ODBC API çağrılarını doğrudan kullanmanız gerekir. Daha fazla bilgi için bkz. [ODBC Programcı başvurusu](/sql/odbc/reference/odbc-programmer-s-reference).

## <a name="how-to-bind-columns-dynamically"></a><a name="_core_how_to_bind_columns_dynamically"></a>Sütunları dinamik olarak bağlama

Sütunları dinamik olarak bağlamak için ek sütunların adlarını bilmeniz (veya belirleyebilmelisiniz) gerekir. Ayrıca ek alan veri üyeleri için depolama alanı ayırmanız, adlarını ve türlerini belirtmeniz ve eklediğiniz sütun sayısını belirtmeniz gerekir.

Aşağıdaki tartışmada iki farklı kayıt kümesi bahsetmektedir. Birincisi, hedef tablodan kayıtları seçen ana kayıt kümesidir. İkincisi, hedef tablonuzun sütunları hakkında bilgi almak için kullanılan özel bir sütun kayıt kümesidir.

### <a name="general-process"></a><a name="_core_the_general_process"></a>Genel Işlem

En genel düzeyde şu adımları izleyin:

1. Ana kayıt kümesi nesnenizi oluşturun.

   İsteğe bağlı olarak, açık bir nesneye bir işaretçi geçirin `CDatabase` veya sütun kayıt kümesine bağlantı bilgilerini başka bir şekilde sağlayabilmeyebilirsiniz.

1. Sütunları dinamik olarak eklemek için gerekli adımları uygulayın.

   Aşağıdaki sütunları ekleme bölümünde açıklanan işleme bakın.

1. Ana kayıt kümenizin açın.

   Kayıt kümesi kayıtları seçer ve hem statik sütunları (kayıt kümesi alan veri üyelerine eşlenmiş) hem de dinamik sütunları (tahsis ettiğiniz ek depolamaya eşlenmiş) bağlamak için kayıt alanı değişimi (RFX) kullanır.

### <a name="adding-the-columns"></a><a name="_core_adding_the_columns"></a>Sütunları ekleme

Çalışma zamanında eklenen sütunları dinamik olarak bağlama, aşağıdaki adımları gerektirir:

1. Çalışma zamanında hangi sütunların hedef tabloda olduğunu belirleme. Bu bilgilerden, kayıt kümesi sınıfınızın tasarlanmasından bu yana tabloya eklenmiş olan sütunların bir listesini ayıklayın.

   Hedef tablo için (sütun adı ve veri türü gibi) sütun bilgileri için veri kaynağını sorgulamak üzere tasarlanan bir sütun kayıt kümesi sınıfını kullanmak iyi bir yaklaşımdır.

1. Yeni alan verisi üyeleri için depolama sağlayın. Ana kayıt kümesi sınıfınızın bilinmeyen sütunlar için alan veri üyeleri olmadığından, adları, sonuç değerlerini ve muhtemelen veri türü bilgilerini depolamak için bir yer sağlamalısınız (sütunlar farklı veri türse).

   Bir yaklaşım bir veya daha fazla dinamik liste oluşturmak, biri yeni sütunların adları, sonuç değerleri için diğeri ve veri türleri için üçüncüsü (gerekliyse). Bu listeler, özellikle değer listesi, bağlamaya yönelik bilgileri ve gerekli depolamayı sağlar. Aşağıdaki şekilde listelerin oluşturulması gösterilmektedir.

   ![Dinamik olarak bağlanacak sütunların listesini oluşturma](../../data/odbc/media/vc37w61.gif "Dinamik olarak bağlanacak sütunların listesini oluşturma")<br/>
   Dinamik olarak bağlanacak sütunların listesini oluşturma

1. Eklenen her sütun için ana kayıt kümenizin işlevine bir RFX işlev çağrısı ekleyin `DoFieldExchange` . Bu RFX çağrıları, ek sütunlar dahil olmak üzere bir kayıt getirme işini ve sütunları kayıt kümesi veri üyelerine ya da bunlar için dinamik olarak sağlanan depolamaya bağlamayı işler.

   Tek yaklaşımda, ana kayıt kümenizin, `DoFieldExchange` Yeni sütunlarınızın listesinden geçen ve listedeki her bir sütun için uygun RFX işlevini çağıran işlevinizin işlevine döngü eklemesi gerekir. Her RFX çağrısında, sütun adı listesinden bir sütun adı ve sonuç değeri listesinin karşılık gelen üyesinde bir depolama konumu geçirin.

### <a name="lists-of-columns"></a><a name="_core_lists_of_columns"></a>Sütun listeleri

Birlikte çalışmanız gereken dört liste aşağıdaki tabloda gösterilmiştir.

|||
|-|-|
|**Geçerli tablo sütunları**| (Çizimde liste 1) Veri kaynağındaki tabloda bulunan sütunların bir listesi. Bu liste, kayıt kümenizde Şu anda bağlı olan sütunların listesiyle eşleşmeyebilir.|
|**Bağlantılı-kayıt kümesi sütunları**| (Çizimde liste 2) Kayıt kümenizde bağlantılı olan sütunların listesi. Bu sütunlarda, işlevinizde RFX deyimleri zaten var `DoFieldExchange` .|
|**----Bağlama sütunları**| (Çizimde liste 3) Tablodaki sütunların listesi, ancak kayıt kümenizde değil. Bunlar dinamik olarak bağlamak istediğiniz sütunlardır.|
|**Dinamik-sütun-değerleri**| (Çizimde 4. liste) Dinamik olarak bağlanan sütunlardan alınan değerler için depolamayı içeren bir liste. Bu listenin öğeleri-----arasında--arasında-tek-bağlanacak sütunlara karşılık gelir.|

### <a name="building-your-lists"></a><a name="_core_building_your_lists"></a>Listelerinizi oluşturma

Göz önünde bulundurmanız gereken genel bir strateji ile ayrıntılara erişebilirsiniz. Bu konunun geri kalanında bulunan yordamlar, [sütun listelerinde](#_core_lists_of_columns)gösterilen listelerin nasıl oluşturulacağını gösterir. Yordamlar şu işlemleri yönlendirecektir:

- [Kayıt kümenizde bulunmayan sütunların adlarını belirleme](#_core_determining_which_table_columns_are_not_in_your_recordset).

- [Tabloya yeni eklenen sütunlar için dinamik depolama sağlama](#_core_providing_storage_for_the_new_columns).

- [Yeni sütunlar IÇIN RFX çağrılarını dinamik olarak ekleme](#_core_adding_rfx_calls_to_bind_the_columns).

### <a name="determining-which-table-columns-are-not-in-your-recordset"></a><a name="_core_determining_which_table_columns_are_not_in_your_recordset"></a>Hangi tablo sütunlarının kayıt kümenizde olmadığını belirleme

Ana kayıt kümenizde zaten bağlantılı olan sütunların bir listesini içeren bir liste (örneğin, bağlantılı kayıt kümesi sütunları) oluşturun. Ardından, veri kaynağındaki tabloda olmayan ancak ana kayıt kümenizde bulunmayan sütun adlarını içeren bir liste oluşturun (geçerli tablo sütunlarından ve bağlı-kayıt kümesi sütunlarından türetilmiş).

##### <a name="to-determine-the-names-of-columns-not-in-the-recordset-columns-to-bind-dynamically"></a>Kayıt kümesinde olmayan sütunların adlarını öğrenmek için (--bind------------

1. Ana kayıt kümenizde zaten bağlantılı olan sütunların listesini (sınırlı kayıt kümesi sütunları) oluşturun.

   Bir yaklaşım, tasarım zamanında bağlantılı kayıt kümesi sütunları oluşturmaktır. Bu adları almak için kayıt kümesinin işlevindeki RFX işlev çağrılarını görsel olarak inceleyebilirsiniz `DoFieldExchange` . Sonra, listenizi adlarıyla başlatılmış bir dizi olarak ayarlayın.

   Örneğin, çizimde, üç öğe ile bağlantılı kayıt kümesi sütunları (liste 2) gösterilmektedir. Bağlantılı kayıt kümesi sütunlarında, geçerli tablo sütunlarında gösterilen telefon sütunu eksik (liste 1).

1. Geçerli tablo sütunlarını ve bağlı-kayıt kümesi sütunlarını, ana kayıt kümenizde zaten bağlanmamış olan sütunların listesini (-bağlanacak-dinamik) bir liste oluşturmak için karşılaştırın.

   Tek bir yaklaşım, çalışma zamanında (geçerli tablo sütunları) tablodaki sütun listenizde ve kayıt kümenizde (bağlantılı-kayıt kümesi-sütunları) zaten bağlamış olan sütunlarınızın listesi ile paralel olarak döngü kullanmaktır. Sütunları bağlama----bağlı kayıt kümesi sütunlarında görünmeyen geçerli tablo sütunlarında adları dinamik olarak koyun.

   Örneğin, çizim sütunları tek bir öğe ile dinamik (liste 3) olarak gösterir: telefon sütunu geçerli tablo sütunlarında (liste 1) bulunur, ancak bağlı-kayıt kümesi sütunlarında (liste 2) değil.

1. Dinamik olarak bağlamak üzere sütunlar listenizde depolanan her bir sütun adına karşılık gelen veri değerlerinin depolanacağı (çizimde liste 4 ' te olduğu gibi) dinamik sütun değerlerinin bir listesini oluşturun (örneğin,-bağlanacak şekilde sütunlar).

   Bu listenin öğeleri yeni kayıt kümesi alanı veri üyelerinin rolünü oynar. Bunlar, dinamik sütunların bağlandığı depolama konumlarıdır. Listelerin açıklamaları için bkz. [sütun listeleri](#_core_lists_of_columns).

### <a name="providing-storage-for-the-new-columns"></a><a name="_core_providing_storage_for_the_new_columns"></a>Yeni sütunlar için depolama sağlama

Sonra, dinamik olarak bağlanacak sütunlar için depolama konumları ayarlayın. Fikir, her sütunun değerini depolamak için bir liste öğesi sağlamaktır. Bu depolama konumları, normalde bağlantılı sütunları depolayan kayıt kümesi üye değişkenlerini paralel olarak alır.

#### <a name="to-provide-dynamic-storage-for-new-columns-dynamic-column-values"></a>Yeni sütunlar için dinamik depolama sağlamak için (dinamik-sütun-değerler)

1. Her bir sütundaki verilerin değerini içerecek şekilde, dinamik-sütun------sütunları arasında paralel olarak sütunlar oluşturun.

   Örneğin, çizim, tek bir öğe ile dinamik sütun-değerlerini (liste 4) gösterir: `CString` geçerli kayıt için gerçek telefon numarasını içeren nesne: "555-1212".

   En yaygın durumda, dinamik sütun-değerlerinde türünde öğeler vardır `CString` . Farklı veri türleri sütunları ile uğraşıyorsanız, çeşitli türlerde öğeler içerebilen bir listeye ihtiyacınız vardır.

Yukarıdaki yordamların sonucu iki ana listedir: sütunlar ve geçerli kayıt için sütunlardaki değerleri içeren dinamik sütun-değer adlarını içeren sütunlar ve dinamik olarak sütunlar.

> [!TIP]
> Yeni sütunlar aynı veri türünde değilse, sütun listesinde her bir karşılık gelen öğenin türünü bir şekilde tanımlayan öğeleri içeren ek bir paralel liste isteyebilirsiniz. (İsterseniz AFX_RFX_BOOL, AFX_RFX_BYTE vb. değerlerini kullanabilirsiniz. Bu sabitler, AFXDB 'de tanımlanmıştır. H.) sütun veri türlerini nasıl temsil ettiğini temel alan bir liste türü seçin.

### <a name="adding-rfx-calls-to-bind-the-columns"></a><a name="_core_adding_rfx_calls_to_bind_the_columns"></a>Sütunları bağlamak için RFX çağrıları ekleme

Son olarak, işlevinizdeki yeni sütunlara yönelik RFX çağrılarını yerleştirerek dinamik bağlamanın gerçekleşmesi için düzenleme yapın `DoFieldExchange` .

##### <a name="to-dynamically-add-rfx-calls-for-new-columns"></a>Yeni sütunlara yönelik RFX çağrılarını dinamik olarak eklemek için

1. Ana kayıt kümenizin `DoFieldExchange` üye işlevinde, yeni sütunlarınız (-to-Bind------------------- Her döngüde,----------arası sütunlarından bir sütun adını ve dinamik-sütun-değerleri sütununun sonuç değerini ayıklayın. Bu öğeleri sütunun veri türüne uygun bir RFX işlev çağrısına geçirin. Listelerin açıklamaları için bkz. [sütun listeleri](#_core_lists_of_columns).

Ortak durumda, `RFX_Text` işlevinizde, aşağıdaki kod satırlarında olduğu gibi listelerden nesneleri ayıkladıktan sonra,------------------------- `CString` ---sütunları olarak `CStringList` adlandırılan `m_listName` ve dinamik sütun değerleri `CStringList` `m_listValue`

```cpp
RFX_Text( pFX,
            m_listName.GetNext( posName ),
            m_listValue.GetNext( posValue ));
```

RFX işlevleri hakkında daha fazla bilgi için bkz. *sınıf kitaplığı başvurusunda* [makrolar ve Globals](../../mfc/reference/mfc-macros-and-globals.md) .

> [!TIP]
> Yeni sütunlar farklı veri türlerdir, her tür için uygun RFX işlevini çağırmak için döngüsünde bir switch ifadesini kullanın.

Çerçeve, `DoFieldExchange` `Open` sütunları kayıt kümesine bağlama işlemi sırasında çağırdığında, bu sütunları bağlayan statik SÜTUNLARA yönelik RFX çağrıları. Sonra döngünüz, dinamik sütunlar için RFX işlevlerini tekrar tekrar çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: büyük veri öğeleri ile çalışma (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)

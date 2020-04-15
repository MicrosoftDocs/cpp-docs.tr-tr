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
ms.openlocfilehash: e26e62b0e8d613c1a09b077e3bf8d01d1eabba66
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367059"
---
# <a name="recordset-dynamically-binding-data-columns-odbc"></a>Kayıt Kümesi: Veri Sütunlarını Dinamik Olarak Bağlama (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Kayıt kümeleri, tasarım zamanında belirttiğiniz bağlama tablo sütunlarını yönetir, ancak tasarım zamanında sizin için bilinmeyen sütunları bağlamak isteyebileceğin durumlar vardır. Bu konu açıklar:

- [Sütunları dinamik olarak bir kayıt kümesine bağlamak istediğinizde.](#_core_when_you_might_bind_columns_dynamically)

- [Sütunları çalışma zamanında dinamik olarak bağlama.](#_core_how_to_bind_columns_dynamically)

> [!NOTE]
> Bu konu, toplu satır `CRecordset` alma nın uygulanmadığı türetilen nesneler için geçerlidir. Toplu satır alma kullanıyorsanız genellikle açıklanan teknikler önerilmez. Toplu satır alma hakkında daha fazla bilgi için bkz: [Recordset: Toplu Olarak Kayıtları Alma (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="when-you-might-bind-columns-dynamically"></a><a name="_core_when_you_might_bind_columns_dynamically"></a>Sütunları Dinamik Olarak Bağlayabildiğinizde

> [!NOTE]
> MFC ODBC Tüketici sihirbazı Visual Studio 2019 ve sonraki yıllarda kullanılamaz. Yine de bir tüketiciyi el ile oluşturabilirsiniz.

Tasarım zamanında, MFC Application Wizard veya [MFC ODBC Consumer Wizard](../../mfc/reference/adding-an-mfc-odbc-consumer.md) **(Add**Class'tan) veri kaynağınızdaki bilinen tablo ve sütunları temel alan kayıt kümesi sınıfları oluşturur. Veritabanları, bunları tasarlarken ve daha sonra uygulamanız bu tabloları ve sütunları çalışma zamanında kullandığında arasında değişebilir. Siz veya başka bir kullanıcı, uygulamanızın kayıt kümesinin dayandığı bir tablodan bir tablo ekleyebilir veya düşürebilir veya sütun lar ekleyebilir veya bırakabilirsiniz. Bu muhtemelen tüm veri erişim uygulamaları için bir endişe değil, ama sizin için ise, nasıl veritabanı şema değişiklikleri ile başa çıkabilirim, yeniden tasarlama kullanabilirsiniz ve yeniden derleme? Bu konunun amacı bu soruyu cevaplamaktır.

Bu konu, sütunları dinamik olarak bağlayabileceğiniz en yaygın durumu açıklar — bilinen bir veritabanı şemasına dayalı bir kayıt kümesiyle başlamış sayılarak, çalışma zamanında ek sütunları işlemek istersiniz. Konu ayrıca, ek sütunların en `CString` yaygın durum olan alan veri üyeleriyle eşlediğini varsayar, ancak öneriler diğer veri türlerini yönetmenize yardımcı olmak için sağlanır.

Az miktarda ekstra kodla şunları yapabilirsiniz:

- [Çalışma zamanında hangi sütunların kullanılabilerini belirleyin.](#_core_how_to_bind_columns_dynamically)

- [Ek sütunları çalışma saatinde, dinamik olarak kayıt setinize bağla.](#_core_adding_the_columns)

Kayıt setiniz, tasarım zamanında bildiğiniz sütunların veri üyelerini hala içerir. Ayrıca, hedef tablonuza yeni sütunlar eklenip eklenmediğini dinamik olarak belirleyen ve bu durumda bu yeni sütunları dinamik olarak ayrılmış depolamaalanına (veri üyelerini kaydetmek yerine) bağlayan küçük miktarda ek kod içerir.

Bu konu, bırakılan tablolar veya sütunlar gibi diğer dinamik bağlama durumlarını kapsamaz. Bu gibi durumlarda, ODBC API çağrılarını daha doğrudan kullanmanız gerekir. Daha fazla bilgi için MSDN Kitaplığı CD'sindeki ODBC SDK *Programcısı* Referansı'na bakın.

## <a name="how-to-bind-columns-dynamically"></a><a name="_core_how_to_bind_columns_dynamically"></a>Sütunları Dinamik Olarak Bağlama

Sütunları dinamik olarak bağlamak için ek sütunların adlarını bilmeniz (veya belirleyebilmeniz) gerekir. Ayrıca ek alan veri üyeleri için depolama ayırmanız, adlarını ve türlerini belirtmeniz ve eklediğiniz sütun sayısını belirtmeniz gerekir.

Aşağıdaki tartışmada iki farklı kayıt kümesinden bahsedilmektedir. Bunlardan ilki, hedef tablodan kayıtları seçen ana kayıt kümesidir. İkincisi, hedef tablonuzdaki sütunlar hakkında bilgi almak için kullanılan özel bir sütun kayıt kümesidir.

### <a name="general-process"></a><a name="_core_the_general_process"></a>Genel Süreç

En genel düzeyde aşağıdaki adımları izleyin:

1. Ana kayıt kümesi nesnenizi oluştur.

   İsteğe bağlı olarak, bir `CDatabase` işaretçiyi açık bir nesneye geçirin veya sütun kayıt kümesine başka bir şekilde bağlantı bilgileri sağlayabilir.

1. Sütunları dinamik olarak eklemek için adımlar atın.

   Aşağıdaki Sütunları Ekleme'de açıklanan işleme bakın.

1. Ana kayıt setinizi açın.

   Recordset, hem statik sütunları (kayıt alanı veri üyelerine eşlenenler) hem de dinamik sütunları (ayırdığınız ekstra depolama alanına eşlenen) bağlamak için kayıtları seçer ve kayıt alanı değişimi (RFX) kullanır.

### <a name="adding-the-columns"></a><a name="_core_adding_the_columns"></a>Sütunekleme

Çalışma zamanında eklenen sütunları dinamik olarak bağlama için aşağıdaki adımlar gerekir:

1. Çalışma saatinde hedef tabloda hangi sütunların olduğunu belirleyin. Bu bilgilerden, kayıt kümesi sınıfınız tasarlandığı günden bu yana tabloya eklenen sütunların bir listesini ayıklayın.

   İyi bir yaklaşım, hedef tablo (sütun adı ve veri türü gibi) için sütun bilgileri için veri kaynağını sorgulamak için tasarlanmış bir sütun kayıt kümesi sınıfı kullanmaktır.

1. Yeni alan veri üyeleri için depolama sağlayın. Ana kayıt kümesi sınıfınızda bilinmeyen sütunlar için alan veri üyeleri olmadığından, adları, sonuç değerlerini ve büyük olasılıkla veri türü bilgilerini depolamak için bir yer sağlamanız gerekir (sütunlar farklı veri türleriise).

   Bir yaklaşım, biri yeni sütunların adları için, diğeri sonuç değerleri için ve üçüncüsü de veri türleri için (gerekirse) bir veya daha fazla dinamik liste oluşturmaktır. Bu listeler, özellikle değer listesi, bilgileri ve bağlama için gerekli depolama sağlar. Aşağıdaki şekil, listelerin oluşturulmasını göstermektedir.

   ![Dinamik olarak bağlatılmak için sütun listeleri oluşturma](../../data/odbc/media/vc37w61.gif "Dinamik olarak bağlatılmak için sütun listeleri oluşturma")<br/>
   Dinamik Olarak Bağlatılabilmek Için Sütun Ların Listelerini Oluşturma

1. Eklenen her sütun için ana kayıt setinizin `DoFieldExchange` işlevine bir RFX işlevi çağrısı ekleyin. Bu RFX çağrıları, ek sütunlar da dahil olmak üzere bir kayıt alma ve sütunları veri üyelerini kaydetmek veya onlar için dinamik olarak sağlanan depolama alanınız için bağlama işini yapar.

   Bir yaklaşım, listedeki her sütun için `DoFieldExchange` uygun RFX işlevini çağırarak, yeni sütun listenizde döngüler ana kaydedicinizin işlevine bir döngü eklemektir. Her RFX çağrısında, sütun adı listesinden bir sütun adı ve sonuç değer listesinin ilgili üyesinde bir depolama konumu geçirin.

### <a name="lists-of-columns"></a><a name="_core_lists_of_columns"></a>Sütun Listeleri

Üzerinde çalışmanız gereken dört liste aşağıdaki tabloda gösterilir.

|||
|-|-|
|**Akım-Tablo-Sütunlar**| (Resimdeki liste 1) Veri kaynağındaki tabloda bulunan sütunların listesi. Bu liste, kayıt setinizde şu anda bağlı olan sütunların listesiyle eşleşebilir.|
|**Bağlı Kayıt Kümesi-Sütunlar**| (Resimdeki liste 2) Kayıt setinizde bağlanan sütunların listesi. Bu sütunlarda zaten işlevinizde `DoFieldExchange` RFX deyimleri bulunur.|
|**Sütunlar-To-Bind-Dinamik**| (Resimdeki liste 3) Tablodaki ancak kayıt setinizde olmayan sütunların listesi. Bunlar dinamik olarak bağlamak istediğiniz sütunlardır.|
|**Dinamik-Sütun-Değerler**| (Resimdeki liste 4) Dinamik olarak bağladığınız sütunlardan alınan değerler için depolama alanı içeren bir liste. Bu listenin öğeleri, Sütunlardan Bine-Dinamik olarak bire bir sütunlara karşılık gelir.|

### <a name="building-your-lists"></a><a name="_core_building_your_lists"></a>Listelerinizi Oluşturma

Genel bir strateji göz önünde bulundurarak, ayrıntılara dönebilirsiniz. Bu konunun geri kalanında ki yordamlar, [Sütun Listeleri'nde](#_core_lists_of_columns)gösterilen listeleri nasıl oluşturabileceğinizi gösterir. Yordamlar size şu yol gösterin:

- [Kayıt setinizde olmayan sütunların adlarını belirleme.](#_core_determining_which_table_columns_are_not_in_your_recordset)

- [Tabloya yeni eklenen sütunlar için dinamik depolama alanı sağlar.](#_core_providing_storage_for_the_new_columns)

- [Dinamik yeni sütunlar için RFX çağrıları ekleme.](#_core_adding_rfx_calls_to_bind_the_columns)

### <a name="determining-which-table-columns-are-not-in-your-recordset"></a><a name="_core_determining_which_table_columns_are_not_in_your_recordset"></a>Kayıt Setinizde Hangi Tablo Sütunlarının Olmadığını Belirleme

Ana kayıt setinizde zaten bağlı olan sütunların listesini içeren bir liste oluşturun (Bağlı-Kayıt Kümesi-Sütunlar, resimde liste 2'deki gibi). Ardından, ana kayıt setinizde değil, veri kaynağındaki tabloda bulunan sütun adlarını içeren bir liste oluşturun (Sütundan Bine-Dinamik olarak, Geçerli Tablo-Sütunlardan ve Bağlı Kayıt Kümesi-Sütunlardan türetilmiştir).

##### <a name="to-determine-the-names-of-columns-not-in-the-recordset-columns-to-bind-dynamically"></a>Kayıt kümesinde olmayan sütunların adlarını belirlemek için (Sütunlardan Bine-Dinamik olarak)

1. Ana kayıt setinizde zaten bağlı olan sütunların bir listesini (Bound-Recordset-Columns) oluşturun.

   Bir yaklaşım, tasarım zamanında Bound-Recordset-Columns oluşturmaktır. Bu adları almak için kayıt kümesinin `DoFieldExchange` işlevindeki RFX işlev çağrılarını görsel olarak inceleyebilirsiniz. Ardından, listenizi adlarla birlikte başharfe bilmiş bir dizi olarak ayarlayın.

   Örneğin, resimde Üç öğeli Bound-Recordset-Columns (Liste 2) gösterilmektedir. Bound-Recordset-Columns'larda Geçerli Tablo Sütunlarında gösterilen Telefon sütunu eksiktir (Liste 1).

1. Ana kayıt setinizde zaten bağlı olmayan sütunların listesini (Sütundan Bine-Dinamik olarak) oluşturmak için Geçerli Tablo-Sütunları ve Bağlı-Kaydedici-Sütunları karşılaştırın.

   Bir yaklaşım, çalışma zamanında tablodaki sütun listenizi (Geçerli Tablo-Sütunlar) ve kayıt setinizde zaten bağlı olan sütun listenizi (Bağlı-Kayıt Kümesi-Sütunlar) paralel olarak döngüye almaktır. Sütunlardan Bine-Dinamik olarak, Bağlı-Kayıt Kümesi-Sütunlarda görünmeyen Geçerli Tablo Sütunlarına herhangi bir ad koyun.

   Örneğin, resimde Sütunlardan Bine-Dinamik olarak (Liste 3) tek bir öğeyle gösterilmektedir: Geçerli Tablo Sütunlarında bulunan Telefon sütunu (Liste 1) ancak Bağlı Kayıt Kümesi Sütunlarında (Liste 2) değildir.

1. Dinamik olarak bağlamak için sütun lar listenizde depolanan her sütun adına karşılık gelen veri değerlerini depolamak için Dinamik Sütun-Değerler listesi (resimdeki Liste 4'teki gibi) oluşturun (Sütunlardan Bine-Dinamik olarak).

   Bu listenin öğeleri yeni kayıt kümesi alan veri üyelerinin rolünü oynar. Bunlar, dinamik sütunların bağlı olduğu depolama konumlarıdır. Listelerin açıklamaları için [sütun listelerine](#_core_lists_of_columns)bakın.

### <a name="providing-storage-for-the-new-columns"></a><a name="_core_providing_storage_for_the_new_columns"></a>Yeni Sütunlar için Depolama Sağlama

Ardından, sütunların dinamik olarak bağlanması için depolama konumları ayarlayın. Fikir, her sütunun değerini depolayacak bir liste öğesi sağlamaktır. Bu depolama konumları, normalde bağlı sütunları depolayan kayıt kümesi üye değişkenlerine paraleldir.

#### <a name="to-provide-dynamic-storage-for-new-columns-dynamic-column-values"></a>Yeni sütunlar için dinamik depolama sağlamak için (Dinamik-Sütun-Değerler)

1. Her sütundaki verilerin değerini içerecek şekilde Sütunlardan Bine-Dinamik olarak paralel dinamik sütun-değerler oluşturun.

   Örneğin, resimde dinamik-sütun değerleri (Liste 4) tek bir `CString` öğe ile gösterir: geçerli kayıt için gerçek telefon numarasını içeren bir nesne: "555-1212".

   En yaygın durumda, Dinamik-Sütun-Değerler türü `CString`elemanları vardır. Farklı veri türlerine sahip sütunlarla uğraşıyorsanız, çeşitli türlerde öğeler içerebilecek bir liste ye ihtiyacınız vardır.

Önceki yordamların sonucu iki ana listedir: Sütunlardan Bine-Dinamik olarak sütunadlarını ve geçerli kaydın sütunlarında bulunan değerleri içeren Dinamik-Sütun Değerleri'ni içeren.

> [!TIP]
> Yeni sütunların tümü aynı veri türünün tümü değilse, sütun listesindeki her karşılık gelen öğenin türünü bir şekilde tanımlayan öğeler içeren ek bir paralel liste isteyebilirsiniz. (İsterseniz bunun için AFX_RFX_BOOL, AFX_RFX_BYTE ve benzeri değerleri kullanabilirsiniz. Bu sabitler AFXDB'de tanımlanır. H.) Sütun veri türlerini nasıl temsil ettiğinize göre bir liste türü seçin.

### <a name="adding-rfx-calls-to-bind-the-columns"></a><a name="_core_adding_rfx_calls_to_bind_the_columns"></a>Sütunları Bağlamak için RFX Çağrıları Ekleme

Son olarak, işlevinizde yeni sütunlar için RFX çağrıları `DoFieldExchange` yerleştirerek dinamik bağlamanın gerçekleşmesini ayarlayın.

##### <a name="to-dynamically-add-rfx-calls-for-new-columns"></a>Dinamik olarak yeni sütunlar için RFX çağrıları eklemek için

1. Ana kayıt setinizin `DoFieldExchange` üye işlevinde, yeni sütunlar (Sütunlardan Bine-Dinamik olarak) listenize geçen kod ekleyin. Her döngüde, Sütunlardan Bine-Dinamik olarak bir sütun adı ve Dinamik-Sütun-Değerleri'nden sütun için bir sonuç değeri ayıklayın. Bu öğeleri, sütunun veri türüne uygun bir RFX işlev çağrısına geçirin. Listelerin açıklamaları için [sütun listelerine](#_core_lists_of_columns)bakın.

Genel olarak, işlevinizde, `RFX_Text` sütunlardan `CString` bine-Dinamik olarak `CStringList` çağrılan ve `m_listName` `CStringList` Dinamik-Sütun-Değerleri'nin çağrıldığı `m_listValue`aşağıdaki kod satırlarında olduğu gibi, listelerden nesneleri ayıklarsınız:

```cpp
RFX_Text( pFX,
            m_listName.GetNext( posName ),
            m_listValue.GetNext( posValue ));
```

RFX işlevleri hakkında daha fazla bilgi için *Sınıf Kitaplığı Başvurusu'ndaki* [Makrolar ve Genel Bilgiler'e](../../mfc/reference/mfc-macros-and-globals.md) bakın.

> [!TIP]
> Yeni sütunlar farklı veri türleriyse, her tür için uygun RFX işlevini çağırmak için döngünüzde bir anahtar deyimi kullanın.

Çerçeve `Open` işlem `DoFieldExchange` sırasında sütunları kaydedici kümeye bağlamaya çağırdığında, RFX statik sütunları bu sütunları bağlar. Sonra döngü tekrar tekrar dinamik sütunlar için RFX işlevleri çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: Büyük Veri Öğeleri ile Çalışma (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)

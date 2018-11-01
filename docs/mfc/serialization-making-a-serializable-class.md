---
title: 'Seri hale getirme: Seri Hale Getirilebilir Bir Sınıf Yapma'
ms.date: 11/04/2016
helpviewer_keywords:
- serializable class [MFC]
- DECLARE_SERIAL macro [MFC]
- default constructor [MFC]
- VERSIONABLE_SCHEMA macro [MFC]
- classes [MFC], derived
- IMPLEMENT_SERIAL macro [MFC]
- no-arguments constructor [MFC]
- Serialize method, overriding
- defaults [MFC], constructor
- CObject class [MFC], deriving serializable classes
- constructors [MFC], defining with no arguments
- serialization [MFC], serializable classes
- no default constructor
ms.assetid: 59a14d32-1cc8-4275-9829-99639beee27c
ms.openlocfilehash: aa9a7f6cb1cb28c701e3954cad27e60cf9f7df4f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486976"
---
# <a name="serialization-making-a-serializable-class"></a>Seri hale getirme: Seri Hale Getirilebilir Bir Sınıf Yapma

Başlıca beş adımı, bir sınıf serileştirilebilir yapmak için gereklidir. Bunlar aşağıda listelenen ve aşağıdaki bölümlerde açıklanmıştır:

1. [CObject'ten sınıfınıza türetme](#_core_deriving_your_class_from_cobject) (veya bazı sınıftan türetilen `CObject`).

1. [Serileştirme üye işlevini geçersiz kılma](#_core_overriding_the_serialize_member_function).

1. [Declare_serıal makrosu kullanarak](#_core_using_the_declare_serial_macro) sınıf bildiriminde.

1. [Bağımsız değişken alan bir oluşturucu tanımlama](#_core_defining_a_constructor_with_no_arguments).

1. [V souboru implementace ımplement_serıal makrosu kullanarak](#_core_using_the_implement_serial_macro_in_the_implementation_file) sınıfınız için.

Eğer `Serialize` doğrudan yerine ile >> ve << operatörleri [CArchive](../mfc/reference/carchive-class.md), son üç adımı serileştirme için gerekli değildir.

##  <a name="_core_deriving_your_class_from_cobject"></a> CObject'ten, sınıf türetme

İşlevselliği ve temel serileştirme Protokolü tanımlanan `CObject` sınıfı. Bir sınıftan türetme tarafından `CObject` (veya türetilmiş sınıftan `CObject`) sınıfın aşağıdaki bildirimde gösterildiği `CPerson`, serileştirme protokol ve işlevlerini erişim `CObject`.

##  <a name="_core_overriding_the_serialize_member_function"></a> Geçersiz kılma üye işlevi seri hale getirme

`Serialize` Tanımlanan üye işlevini `CObject` sınıfı, bir nesnenin geçerli durumu yakalamak için gerekli verilere serileştirmek için sorumludur. `Serialize` İşleve sahip bir `CArchive` okuma ve yazma nesne verilerini kullanan bağımsız değişken. [CArchive](../mfc/reference/carchive-class.md) nesnesinde bir üye işlev `IsStoring`, gösteren olmadığını `Serialize` (veri yazma) depolamak veya (veri okuma) yükleniyor. Sonuçlarını kullanarak `IsStoring` bir kılavuz olarak ya da nesnenizin verilerinde eklediğiniz `CArchive` nesne ekleme işleciyle (**<\<**) veya çıkarma işleci (veriayıklama **>>**).

Türetilen bir sınıf göz önünde bulundurun `CObject` ve türlerinin iki yeni üye değişkeni yok `CString` ve **WORD**. Aşağıdaki sınıf bildiriminin parçası yeni üye değişkenleri ve bildirimi için geçersiz kılınan gösterir `Serialize` üye işlevi:

[!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_1.h)]

#### <a name="to-override-the-serialize-member-function"></a>Serileştirme üye işlev geçersiz kılınamıyor

1. Temel sınıf sürümünüz çağrı `Serialize` devralınan bölümü nesnenin serileştirildiği emin olmak için.

1. Ekleme veya sınıfınıza belirli üye değişkenleri ayıklar.

   Ekleme ve çıkarma işleçleri veri okuma ve yazma için arşiv sınıfı ile etkileşim kurun. Aşağıdaki örnek nasıl uygulayacağınızı gösteren `Serialize` için `CPerson` sınıfı bildirilen yukarıda:

   [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_2.cpp)]

Ayrıca [CArchive::Read](../mfc/reference/carchive-class.md#read) ve [CArchive::Write](../mfc/reference/carchive-class.md#write) okuma ve yazma, çok miktarda yazılmayan veri üye işlevleri.

##  <a name="_core_using_the_declare_serial_macro"></a> Declare_serıal makrosu kullanma

Declare_serıal makrosu, burada gösterildiği gibi seri hale getirme, destekleyen sınıfları bildiriminde gereklidir:

[!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_3.h)]

##  <a name="_core_defining_a_constructor_with_no_arguments"></a> Bir oluşturucu bağımsız değişken olmadan tanımlama

MFC varsayılan bir oluşturucu gerektirir (diskten yüklenir), seri olarak nesnelerinizi yeniden oluşturur. Seri durumdan çıkarma işlemi, tüm üye değişkenlerinde nesneyi yeniden oluşturmak için gereken değerleri ile doldurur.

Bu oluşturucu, genel, korumalı veya özel olarak bildirilebilir. Korumalı veya özel değişiklik yaparsanız serileştirme işlevleri tarafından yalnızca kullanım biçimine sağlanmasına yardımcı olur. Oluşturucu, gerekirse silinmesine izin veren bir durumda nesne yerleştirmeniz gerekir.

> [!NOTE]
>  Declare_serıal ve ımplement_serıal makroları kullanan bir sınıf içinde bağımsız değişken içermeyen bir kurucu tanımlamak, parantezi unutsanız bile ımplement_serıal makrosu kullanıldığı satırında "hiçbir varsayılan oluşturucu yok" derleyici uyarısı alırsınız.

##  <a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a> V Souboru İmplementace ımplement_serıal makrosu kullanma

Implement_serıal makrosu çeşitli işlevler olduğunda, türetilen seri hale getirilebilir bir sınıf tanımlamak için kullanılan `CObject`. V souboru implementace Bu makroyu kullanın (. CPP) sınıfınız için. Makro ilk iki bağımsız değişkenleri sınıfın adını ve hemen kendi taban sınıfının adı var.

Bu makro üçüncü bağımsız değişkeni bir şema sayıdır. Aslında bir sürüm numarası sınıfındaki nesneler için şema sayıdır. Büyük veya 0'a eşit bir tamsayı şema numara için kullanın. (Bu şema sayı veritabanı terminolojisi ile karıştırmayın.)

MFC serileştirme kod nesneleri belleğe okuma sırasında şema numarasını denetler. Disk nesnesinde şema sayısını bellek sınıfında şema sayısı eşleşmezse kitaplığı oluşturur bir `CArchiveException`, programınızı nesnesi yanlış bir sürümü okumasını engelliyor.

İsterseniz, `Serialize` birden çok sürümü okuyabilir için üye işlevini — diğer bir deyişle, uygulamanın farklı sürümlerini yazılmış dosyalar — değeri kullanabilirsiniz *versıonable_schema* ımplement_serıal bağımsız değişkeni olarak Makro. Kullanım bilgilerini ve bir örnek için bkz: `GetObjectSchema` sınıfının üye işlevinde `CArchive`.

Aşağıdaki örnek, bir sınıf için ımplement_serıal işlemi gösterilir `CPerson`, yani türetilen `CObject`:

[!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_4.cpp)]

Seri hale getirilebilir bir sınıf oluşturduktan sonra makalesinde açıklandığı gibi bir sınıfın nesnelerini serileştirebiliyorsa [seri hale getirme: bir nesneyi serileştirmek](../mfc/serialization-serializing-an-object.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Serileştirme](../mfc/serialization-in-mfc.md)


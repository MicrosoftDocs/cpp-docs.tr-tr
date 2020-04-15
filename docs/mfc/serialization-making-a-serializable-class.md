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
ms.openlocfilehash: 9648bd4f516a5f174534336b1ca3b42bb51ca0c4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372714"
---
# <a name="serialization-making-a-serializable-class"></a>Seri hale getirme: Seri Hale Getirilebilir Bir Sınıf Yapma

Bir sınıfı serileştirilebilir hale getirmek için beş ana adım gereklidir. Aşağıda listelenmiş ve aşağıdaki bölümlerde açıklanmıştır:

1. [Sınıfınızı CObject'ten](#_core_deriving_your_class_from_cobject) (veya türetilen bazı `CObject`sınıftan) türetme.

1. [Serialize üye işlevini geçersiz kılma.](#_core_overriding_the_serialize_member_function)

1. Sınıf bildiriminde [DECLARE_SERIAL makroyu kullanma.](#_core_using_the_declare_serial_macro)

1. [Hiçbir bağımsız değişken alan bir oluşturucu tanımlama.](#_core_defining_a_constructor_with_no_arguments)

1. Sınıfınız için [uygulama dosyasındaki IMPLEMENT_SERIAL makroyu kullanma.](#_core_using_the_implement_serial_macro_in_the_implementation_file)

`Serialize` [CArchive'in](../mfc/reference/carchive-class.md) >> ve << işleçleri aracılığıyla doğrudan değil de doğrudan ararsanız, serileştirme için son üç adım gerekmez.

## <a name="deriving-your-class-from-cobject"></a><a name="_core_deriving_your_class_from_cobject"></a>CObject'ten Sınıfınızı Türetme

Temel serileştirme protokolü ve işlevselliği `CObject` sınıfta tanımlanır. Aşağıdaki `CObject` sınıf `CObject` `CPerson`bildiriminde gösterildiği gibi, sınıfınızı (veya türetilmiş bir sınıftan) türeterek, serileştirme `CObject`protokolüne ve işlevinize erişebilirsiniz.

## <a name="overriding-the-serialize-member-function"></a><a name="_core_overriding_the_serialize_member_function"></a>Serialize Üye İşlevi geçersiz kılma

`CObject` Sınıfta tanımlanan `Serialize` üye işlev, bir nesnenin geçerli durumunu yakalamak için gereken verileri seri hale getirmekten sorumludur. İşlev, `Serialize` `CArchive` nesne verilerini okumak ve yazmak için kullandığı bir bağımsız değişkene sahiptir. [CArchive nesnesi,](../mfc/reference/carchive-class.md) `IsStoring`depolama (veri `Serialize` yazma) veya yükleme (veri okuma) olup olmadığını gösteren bir üye işlevi vardır. `IsStoring` Kılavuz olarak sonuçları kullanarak, nesnenizin verilerini ekleme işleci `CArchive` (**<**) ile nesneye ekler veya çıkarma işleci yle veri ayıklarsınız ( ).**>>**

Tür ve `CObject` **WORD'den**türetilen ve iki yeni `CString` üye değişkeni olan bir sınıf düşünün. Aşağıdaki sınıf bildirimi parçası yeni üye değişkenleri ve geçersiz `Serialize` olan üye işlev için bildirimi gösterir:

[!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_1.h)]

#### <a name="to-override-the-serialize-member-function"></a>Serialize üye işlevini geçersiz kılmak için

1. Nesnenin `Serialize` devralınan bölümünün seri hale diğinden emin olmak için taban sınıf sürümünüzü arayın.

1. Sınıfınıza özel üye değişkenleri ekleyin veya ayıklayın.

   Ekleme ve çıkarma işleçleri, verileri okumak ve yazmak için arşiv sınıfıyla etkileşime girer. Aşağıdaki örnek, yukarıda `Serialize` bildirilen `CPerson` sınıf için nasıl uygulanacağını gösterir:

   [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_2.cpp)]

[CArchive::Oku](../mfc/reference/carchive-class.md#read) ve [CArchive::Büyük](../mfc/reference/carchive-class.md#write) miktarda yazılmamış veriyi okumak ve yazmak için üye işlevleri yazın.:CArchive'i de kullanabilirsiniz.

## <a name="using-the-declare_serial-macro"></a><a name="_core_using_the_declare_serial_macro"></a>DECLARE_SERIAL Makrosu Kullanma

DECLARE_SERIAL makroburada gösterildiği gibi, serileştirme yi destekleyecek sınıfların bildiriminde gereklidir:

[!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_3.h)]

## <a name="defining-a-constructor-with-no-arguments"></a><a name="_core_defining_a_constructor_with_no_arguments"></a>Bağımsız Değişkensiz Bir Oluşturucu Tanımlama

MFC, nesneleriniz deserialized (diskten yüklendi) olarak yeniden oluşturduğunda varsayılan bir oluşturucu gerektirir. Deserialization işlemi nesneyi yeniden oluşturmak için gerekli değerleri ile tüm üye değişkenleri dolduracaktır.

Bu yapıcı kamuya açık, korumalı veya özel olarak ilan edilebilir. Korumalı veya özel hale getirirseniz, yalnızca serileştirme işlevleri tarafından kullanıldığından emin olursunuz. Oluşturucu, nesneyi gerekirse silinmesine izin veren bir duruma koymalıdır.

> [!NOTE]
> DECLARE_SERIAL ve IMPLEMENT_SERIAL makroları kullanan bir sınıfta bağımsız değişkeni olmayan bir oluşturucu tanımlamayı unutursanız, IMPLEMENT_SERIAL makronun kullanıldığı satırda "varsayılan oluşturucu yok" derleyicisi uyarısı alırsınız.

## <a name="using-the-implement_serial-macro-in-the-implementation-file"></a><a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a>Uygulama Dosyasında IMPLEMENT_SERIAL Makrosu Kullanma

IMPLEMENT_SERIAL makrosu, `CObject`serializable bir sınıf türettiğinizde gereken çeşitli işlevleri tanımlamak için kullanılır. Bu makroyu uygulama dosyasında kullanıyorsunuz (. CPP) sınıf için. Makroya ilk iki bağımsız değişken sınıfın adı ve hemen taban sınıfının adıdır.

Bu makronun üçüncü bağımsız değişkeni şema numarasıdır. Şema numarası aslında sınıfın nesneleri için bir sürüm numarasıdır. Şema numarası için 0'dan büyük veya eşit bir tamsayı kullanın. (Bu şema numarasını veritabanı terminolojisi ile karıştırmayın.)

MFC serileştirme kodu, nesneleri belleğe okurken şema numarasını denetler. Diskteki nesnenin şema sayısı bellekteki sınıfın şema numarasıyla eşleşmiyorsa, kitaplık, programınızın nesnenin yanlış bir sürümünü okumasını engelleyen bir `CArchiveException`

Üye işlevinizin `Serialize` birden çok sürümü (diğer bir şekilde uygulamanın farklı sürümleriyle yazılmış dosyaları) okuyabilmesini istiyorsanız, *IMPLEMENT_SERIAL* makrosu için VERSIONABLE_SCHEMA değerini kullanabilirsiniz. Kullanım bilgileri ve bir örnek `GetObjectSchema` için sınıfın `CArchive`üye işlevine bakın.

Aşağıdaki örnek, bir sınıf için IMPLEMENT_SERIAL `CPerson`nasıl kullanılacağını `CObject`gösterir, bu türetilmiştir:

[!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_4.cpp)]

Serileştirilebilir bir sınıfa sahip olduktan sonra, [Serileştirme: Nesneyi Serileştirme](../mfc/serialization-serializing-an-object.md)makalesinde belirtildiği gibi sınıfın nesnelerini serihale edebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Serileştirme](../mfc/serialization-in-mfc.md)

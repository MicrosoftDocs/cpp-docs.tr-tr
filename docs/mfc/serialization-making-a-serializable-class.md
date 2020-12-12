---
description: 'Şu konuda daha fazla bilgi edinin: seri hale getirilebilir bir sınıf oluşturma'
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
ms.openlocfilehash: 21c45887199768094953066818acfe1b87d8d45d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217542"
---
# <a name="serialization-making-a-serializable-class"></a>Seri hale getirme: Seri Hale Getirilebilir Bir Sınıf Yapma

Bir sınıfı seri hale getirilebilir hale getirmek için beş ana adım gereklidir. Bunlar aşağıda listelenmiştir ve aşağıdaki bölümlerde açıklanmıştır:

1. [Sınıfınızı CObject 'Ten türeten](#_core_deriving_your_class_from_cobject) (veya ondan türetilmiş bazı bir sınıftan `CObject` ).

1. [Serileştirme üye Işlevini geçersiz kılma](#_core_overriding_the_serialize_member_function).

1. Sınıf bildiriminde [DECLARE_SERIAL makrosunu kullanma](#_core_using_the_declare_serial_macro) .

1. [Bağımsız değişken alan bir Oluşturucu tanımlama](#_core_defining_a_constructor_with_no_arguments).

1. Sınıfınız için [uygulama dosyasında IMPLEMENT_SERIAL makrosunu kullanma](#_core_using_the_implement_serial_macro_in_the_implementation_file) .

`Serialize` [CArchive](../mfc/reference/carchive-class.md)'ın >> ve << işleçleri yerine doğrudan çağrı yaparsanız, son üç adım serileştirme için gerekli değildir.

## <a name="deriving-your-class-from-cobject"></a><a name="_core_deriving_your_class_from_cobject"></a> CObject 'ten sınıfınızı türeten

Temel serileştirme Protokolü ve işlevselliği `CObject` sınıfında tanımlanmıştır. `CObject`Aşağıdaki sınıf bildiriminde gösterildiği gibi, sınıfınızı sınıfından türeterek (veya öğesinden türetilmiş bir sınıftan `CObject` ), `CPerson` serileştirme protokolüne ve işlevlerine erişim elde edersiniz `CObject` .

## <a name="overriding-the-serialize-member-function"></a><a name="_core_overriding_the_serialize_member_function"></a> Serileştirme üye Işlevini geçersiz kılma

`Serialize`Sınıfında tanımlanmış member işlevi, `CObject` nesnenin geçerli durumunu yakalamak için gereken verilerin gerçekten serileştirilmesinden sorumludur. `Serialize`İşlevin `CArchive` nesne verilerini okumak ve yazmak için kullandığı bir bağımsız değişkeni vardır. [CArchive](../mfc/reference/carchive-class.md) nesnesi, `IsStoring` `Serialize` depolama (veri yazma) veya yükleme (verileri okuma) durumunu gösteren bir üye işlevi içerir. Kılavuz olarak sonucunu kullanarak `IsStoring` , nesne verilerini `CArchive` nesnesine ekleme işleci () ile eklersiniz **<\<**) or extract data with the extraction operator (**>>** .

Türünden türetilmiş `CObject` ve iki yeni üye değişkenine (tür ve sözcük) sahip olan bir sınıfı `CString` düşünün . Aşağıdaki sınıf bildirim parçası, geçersiz kılınan üye işlevi için yeni üye değişkenlerini ve bildirimini gösterir `Serialize` :

[!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_1.h)]

#### <a name="to-override-the-serialize-member-function"></a>Serileştirme üye işlevini geçersiz kılmak için

1. `Serialize`Nesnenin devralınmış bölümünün serileştirilmekte olduğundan emin olmak için temel sınıf sürümünüzü çağırın.

1. Sınıfınıza özgü üye değişkenlerini ekleyin veya ayıklayın.

   Ekleme ve ayıklama işleçleri, verileri okumak ve yazmak için Arşiv sınıfıyla etkileşime geçin. Aşağıdaki örnek, `Serialize` yukarıda belirtilen sınıf için nasıl uygulanacağını gösterir `CPerson` :

   [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_2.cpp)]

Ayrıca, büyük miktarlarda türsüz verileri okumak ve yazmak için [CArchive:: Read](../mfc/reference/carchive-class.md#read) ve [CArchive:: Write](../mfc/reference/carchive-class.md#write) üye işlevlerini de kullanabilirsiniz.

## <a name="using-the-declare_serial-macro"></a><a name="_core_using_the_declare_serial_macro"></a> DECLARE_SERIAL makrosunu kullanma

DECLARE_SERIAL makrosu, burada gösterildiği gibi, serileştirme desteği sağlayacak sınıfların bildiriminde gereklidir:

[!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_3.h)]

## <a name="defining-a-constructor-with-no-arguments"></a><a name="_core_defining_a_constructor_with_no_arguments"></a> Bağımsız değişken Içermeyen bir Oluşturucu tanımlama

MFC, nesneleri seri durumdan çıkardıkları (diskten yüklenen) yeniden oluşturduğunda varsayılan bir Oluşturucu gerektirir. Seri durumdan çıkarma işlemi, nesneyi yeniden oluşturmak için gereken değerlerle birlikte tüm üye değişkenlerini dolduracaktır.

Bu Oluşturucu ortak, korumalı veya özel olarak bildirilemez. Korumalı veya özel yaparsanız, yalnızca serileştirme işlevleri tarafından kullanılacak olduğundan emin olun. Oluşturucunun nesneyi, gerekirse silinmesine izin veren bir duruma koymalıdır.

> [!NOTE]
> DECLARE_SERIAL ve IMPLEMENT_SERIAL makrolarını kullanan bir sınıfta bağımsız değişken olmadan bir Oluşturucu tanımlamanızı unutursanız, IMPLEMENT_SERIAL makronun kullanıldığı satırda "Varsayılan Oluşturucu yok" derleyici uyarısı alırsınız.

## <a name="using-the-implement_serial-macro-in-the-implementation-file"></a><a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a> Uygulama dosyasında IMPLEMENT_SERIAL makrosunu kullanma

IMPLEMENT_SERIAL makrosu, öğesinden serileştirilebilir bir sınıfı türettiğinizde gereken çeşitli işlevleri tanımlamak için kullanılır `CObject` . Bu makroyu uygulama dosyasında (. CPP). Makronun ilk iki bağımsız değişkeni, sınıfın adı ve anlık temel sınıfının adıdır.

Bu makronun üçüncü bağımsız değişkeni bir şema numarasıdır. Şema numarası aslında sınıfının nesneleri için bir sürüm numarasıdır. Şema numarası için 0 ' dan büyük veya buna eşit bir tamsayı kullanın. (Bu şema numarasını veritabanı terminolojisi ile karıştırmayın.)

MFC serileştirme kodu nesneleri belleğe okurken şema numarasını denetler. Diskteki nesnenin şema numarası, bellekteki sınıfın şema numarasıyla eşleşmezse, kitaplık bir oluşturur `CArchiveException` ve bu da programınızın nesnenin yanlış bir sürümünü okumasını önler.

`Serialize`Üye işlevinizin birden çok sürümü okuyabilmesini istiyorsanız — Yani, uygulamanın farklı sürümleriyle yazılmış dosyalar — *VERSIONABLE_SCHEMA* değerini IMPLEMENT_SERIAL makrosunda bağımsız değişken olarak kullanabilirsiniz. Kullanım bilgileri ve bir örnek için bkz `GetObjectSchema` . sınıfının üye işlevi `CArchive` .

Aşağıdaki örnek, ' den türetilen bir sınıf için IMPLEMENT_SERIAL nasıl kullanacağınızı gösterir `CPerson` `CObject` :

[!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_4.cpp)]

Seri hale getirilebilir bir sınıfınız olduktan sonra, [serileştirme: bir nesneyi seri hale getirme](../mfc/serialization-serializing-an-object.md)makalesinde anlatıldığı gibi sınıfının nesnelerini seri hale getirebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Serileştirme](../mfc/serialization-in-mfc.md)

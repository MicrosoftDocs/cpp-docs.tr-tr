---
title: 'Seri hale getirme: seri hale getirilebilir bir sınıf yapma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4412e8db861ac522c0f1b1d7192bfbb83612d64c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="serialization-making-a-serializable-class"></a>Seri hale getirme: Seri Hale Getirilebilir Bir Sınıf Yapma
Beş ana adım seri hale getirilebilir bir sınıf yapmak için gereklidir. Aşağıda listelenen bağlıdır ve aşağıdaki bölümlerde açıklanmıştır:  
  
1.  [CObject'ten, sınıf türetme](#_core_deriving_your_class_from_cobject) (veya bazı sınıfından türetilen `CObject`).  
  
2.  [Serileştirme üye işlevi geçersiz kılma](#_core_overriding_the_serialize_member_function).  
  
3.  [Declare_serıal makrosu kullanarak](#_core_using_the_declare_serial_macro) sınıf bildirimindeki.  
  
4.  [Bağımsız değişken almayan bir oluşturucu tanımlama](#_core_defining_a_constructor_with_no_arguments).  
  
5.  [Implement_serıal makrosu uygulama dosyasındaki kullanarak](#_core_using_the_implement_serial_macro_in_the_implementation_file) sınıfınız için.  
  
 Çağırırsanız `Serialize` doğrudan yerine ile >> ve << operatörleri [CArchive](../mfc/reference/carchive-class.md), önceki üç adımı serileştirme için gerekli değildir.  
  
##  <a name="_core_deriving_your_class_from_cobject"></a> CObject'ten, sınıf türetme  
 İşlevselliği ve temel serileştirme Protokolü tanımlanan `CObject` sınıfı. Sınıfından türetilen tarafından `CObject` (veya türetilen bir sınıftan `CObject`) sınıfı aşağıdaki bildiriminde gösterildiği gibi `CPerson`, serileştirme protokolü ve işlevselliğini erişim `CObject`.  
  
##  <a name="_core_overriding_the_serialize_member_function"></a> Geçersiz kılma seri üye işlevi  
 `Serialize` Tanımlanan üye işlevi `CObject` sınıfı, bir nesnenin geçerli durumu yakalamak için gerekli verilere serileştirmek için sorumludur. `Serialize` İşlevine sahip bir `CArchive` nesne verilerini okuma ve yazma için kullandığı bağımsız değişkeni. [CArchive](../mfc/reference/carchive-class.md) nesneye sahip bir üye işlevi `IsStoring`, belirten olup olmadığını `Serialize` (veri yazma) saklamak veya (veri okuma) yükleniyor. Sonuçları kullanarak `IsStoring` bir kılavuz olarak, ya da, nesnenin verilerde ekleme `CArchive` ekleme işleci nesnesiyle (**<\<**) veya veri çıkarma işleci (Ayıkla **>>**).  
  
 Türetilmiş bir sınıf göz önünde bulundurun `CObject` ve türlerinin iki yeni üye değişkeni yok `CString` ve **WORD**. Aşağıdaki sınıf bildirimi parça yeni üye değişkenleri ve geçersiz kılınan bildirimi gösterir `Serialize` üye fonksiyonu:  
  
 [!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_1.h)]  
  
#### <a name="to-override-the-serialize-member-function"></a>Serileştirme üye işlevi geçersiz kılmak için  
  
1.  Taban sınıfı sürümünüz çağrı `Serialize` nesne devralınan kısmı seri hale getirilmiş emin olmak için.  
  
2.  INSERT veya sınıfınıza belirli üye değişkenleri ayıklar.  
  
     Ekleme ve çıkarma işleçleri okumak ve yazmak için arşiv sınıfı ile etkileşim. Aşağıdaki örnekte nasıl uygulanacağını gösterir `Serialize` için `CPerson` sınıf bildirilen yukarıda:  
  
     [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_2.cpp)]  
  
 Aynı zamanda [CArchive::Read](../mfc/reference/carchive-class.md#read) ve [CArchive::Write](../mfc/reference/carchive-class.md#write) okumak ve büyük miktarlarda yazılmayan veri yazmak için üye işlevleri.  
  
##  <a name="_core_using_the_declare_serial_macro"></a> Declare_serıal makrosu kullanma  
 `DECLARE_SERIAL` Makrosu, serileştirme, destekleyen sınıfları bildiriminde gereklidir, aşağıda gösterildiği gibi:  
  
 [!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_3.h)]  
  
##  <a name="_core_defining_a_constructor_with_no_arguments"></a> Bağımsız değişken içermeyen bir oluşturucuya tanımlama  
 MFC varsayılan bir oluşturucu gerektirir (diskten yüklenir), seri olarak nesnelerinizi yeniden oluşturur. Seri durumdan çıkarma işlemi tüm üye değişkenleri nesneyi yeniden oluşturmak için gereken değerleri ile doldurur.  
  
 Bu oluşturucu, public, korumalı ya da özel bildirilebilir. Korumalı veya özel değişiklik yaparsanız, yalnızca serileştirme işlevleri tarafından kullanılacağını sağlanmasına yardımcı olur. Oluşturucusu gerekirse silinmesine izin veren bir durumda nesne konulmalıdır.  
  
> [!NOTE]
>  Bağımsız değişken içermeyen bir oluşturucuya kullanan bir sınıfı tanımlamak unutursanız `DECLARE_SERIAL` ve `IMPLEMENT_SERIAL` makroları satırda "varsayılan oluşturucu yok kullanılabilir" derleyici uyarısı alırsınız nerede `IMPLEMENT_SERIAL` makrosu kullanılır.  
  
##  <a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a> Implement_serıal makrosu uygulama dosyasında kullanma  
 `IMPLEMENT_SERIAL` Makrosu olduğunda, türetilen seri hale getirilebilir bir sınıf çeşitli işlevleri tanımlamak için kullanılan `CObject`. Uygulama dosyasında bu makrosu kullanın (. CPP) sınıfınız için. İlk iki makrosu için sınıfı adı ve hemen kendi temel sınıfının adını değişkendir.  
  
 Bu makrosu üçüncü bağımsız değişkeni bir şema sayıdır. Aslında bir sürüm numarası sınıfındaki nesneler için şema sayıdır. Büyük veya 0 değerine eşit bir tamsayı için şema numarasını kullanın. (Bu veritabanı terminolojisi şema numarasıyla karıştırmayın.)  
  
 MFC seri hale getirme kodu şema numarasını nesneleri belleğe okunurken denetler. Disk nesnesinde şema sayısı bellek sınıfında şema sayısı eşleşmiyorsa, kitaplık özel durum oluşturacak bir `CArchiveException`, programınızı nesne yanlış sürümünü okumasını engelliyor.  
  
 İsterseniz, `Serialize` üye işlevi birden çok sürümü okuyabilir — diğer bir deyişle, uygulamanın farklı sürümlerini yazılmış dosyaları — değer kullanabilirsiniz **versıonable_schema** bağımsız değişken olarak `IMPLEMENT_SERIAL` Makro. Kullanım bilgilerini ve bir örnek için bkz: `GetObjectSchema` sınıfının üye işlevini `CArchive`.  
  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `IMPLEMENT_SERIAL` bir sınıf için `CPerson`, yani türetilmiş `CObject`:  
  
 [!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_4.cpp)]  
  
 Seri hale getirilebilir bir sınıf olduktan sonra makalesinde ele alındığı gibi sınıfın nesnelerini serileştirebilen [seri hale getirme: bir nesneyi seri hale getirme](../mfc/serialization-serializing-an-object.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Serileştirme](../mfc/serialization-in-mfc.md)


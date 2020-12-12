---
description: 'Daha fazla bilgi edinin: ad alanları ve tür görünürlüğü (C++/CX)'
title: Ad alanları ve tür görünürlüğü (C++/CX)
ms.date: 12/30/2016
ms.assetid: cbc01a3a-3b69-4ded-9c42-ecbf0fd0a00e
ms.openlocfilehash: 014791ef322538c824c68409681d7fb856e1c837
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282906"
---
# <a name="namespaces-and-type-visibility-ccx-"></a>Ad alanları ve tür görünürlüğü (C++/CX)

Ad alanı, ilgili işlevselliğe sahip ve kitaplıklarda ad çakışmalarını önlemek için standart bir C++ yapısıdır. Windows Çalışma Zamanı tür sistemi, kendi kodunuzla birlikte tüm ortak Windows Çalışma Zamanı türlerinin ad uzayı kapsamındaki bir ad alanında bildirilmesini gerektirir. Genel kapsamda veya başka bir sınıfın içinde iç içe yerleştirilmiş genel türler derleme zamanı hatasına neden olur.

Bir. winmd dosyası, kök ad alanıyla aynı ada sahip olmalıdır. Örneğin, A. B. C. MyClass adlı bir sınıf, yalnızca bir. winmd veya A. B. winmd veya A. B. C. winmd adında bir meta veri dosyasında tanımlanmışsa oluşturulabilir. Yürütülebilir dosyanın adı. winmd dosya adıyla eşleşmek için gerekli değildir.

## <a name="type-visibility"></a>Tür görünürlüğü

Bir ad alanında, Windows Çalışma Zamanı türler — standart C++ türlerinden farklı olarak, Private veya public erişilebilirliğe sahiptir. Varsayılan olarak, erişilebilirlik özeldir. Yalnızca genel bir tür meta veriler görünür ve bu nedenle, C++ dışındaki dillerde yazılmış olabilecek uygulamalardan ve bileşenlerden tüketilebilir. Genel olarak, görünür türler .NET dillerinde veya JavaScript 'te desteklenmeyen C++ özel kavramlarını sunamadığından, görünür türler için kurallar, görünür olmayan türler için kurallara göre daha kısıtlayıcıdır.

> [!NOTE]
> Meta veriler yalnızca .NET dilleri ve JavaScript tarafından çalışma zamanında tüketilebilir. C++ uygulaması veya bileşeni, başka bir C++ uygulaması veya bileşeniyle görüşülürken — C++ dilinde yazılmış olan Windows bileşenlerini içerir, ardından meta verilerin çalışma zamanı tüketimine gerek yoktur.

## <a name="member-accessibility-and-visibility"></a>Üye erişilebilirliği ve görünürlüğü

Özel bir başvuru sınıfında, arabiriminde veya temsilcisinde, genel erişilebilirliğe sahip olsalar dahi hiçbir üye meta veriye dağıtılır. Ortak başvuru sınıflarında, meta verilerde bulunan üyelerin görünürlüğünü, kaynak kodunuzda erişilebilirliklerini bağımsız olarak kontrol edebilirsiniz. Standart C++ ' da olduğu gibi, en az ayrıcalık ilkesini uygulayın; Kesinlikle olması gerekmedikçe, üyelerinizden meta verilerde görünür yapmayın.

Hem meta veri görünürlüğünü hem de kaynak kodu erişilebilirliğini denetlemek için aşağıdaki erişim değiştiricilerini kullanın.

| Değiştirici | Anlamı | Meta verilere mi yayılsın? |
|--|--|--|
| **`private`** | Varsayılan erişilebilirlik. Standart C++ ile aynı anlamı. | Hayır |
| **`protected`** | Standart C++ ile aynı anlamı, hem uygulama hem de bileşen içinde ve meta verilerde. | Evet |
| **`public`** | Standart C++ ile aynı anlamı. | Evet |
| **`public protected`** veya **`protected public`** | Meta verilerde korunan erişilebilirlik, uygulama veya bileşen içinde ortak. | Evet |
| **`protected private`** veya **`private protected`** | Meta verilerde görünmez; uygulama veya bileşen içinde korunan erişilebilirlik. |  |
| **`internal`** veya **`private public`** | Üye Uygulama veya bileşen içinde ortaktır, ancak meta verilerde görünür değildir. | Hayır |

## <a name="windows-runtime-namespaces"></a>Windows Çalışma Zamanı ad alanları

Windows API, Windows:: Namespaces içinde belirtilen türlerden oluşur \* . Bu ad alanları Windows için ayrılmıştır ve türleri bunlara eklenemez. **Nesne tarayıcısı**, bu ad alanlarını Windows. winmd dosyasında görüntüleyebilirsiniz. Bu ad alanları hakkındaki belgeler için bkz. [WINDOWS API](/uwp/api/).

## <a name="ccx-namespaces"></a>C++/CX ad alanları

C++/CX, Windows Çalışma Zamanı türü sisteminin projeksiyonunun bir parçası olarak bu ad alanlarında belirli türleri tanımlar.

| Ad Alanı | Açıklama |
|--|--|
| default | Yerleşik sayısal ve Char16 türlerini içerir. Bu türler her ad alanındaki kapsamdadır ve bir **`using`** ifade hiçbir şekilde gerekli değildir. |
| `Platform` | ,, Ve gibi Windows çalışma zamanı türlerine karşılık gelen öncelikle genel türler `Array<T>` içerir `String` `Guid` `Boolean` . Ayrıca, ve gibi özelleştirilmiş yardımcı türler `Platform::Agile<T>` içerir `Platform::Box<T>` . |
| `Platform::Collections` | Windows Çalışma Zamanı koleksiyonu arabirimlerini uygulayan somut koleksiyon sınıflarını içerir `IVector` `IMap` . Bu türler, platform. winmd içinde değil, Collection. h üstbilgi dosyasında tanımlanmıştır. |
| `Platform::Details` | Derleyici tarafından kullanılan ve genel tüketim için amaçlanmış türler içerir. |

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi (C++/CX)](../cppcx/type-system-c-cx.md)

---
title: Ad alanları ve tür görünürlüğü (C + +/ CX)
ms.date: 12/30/2016
ms.assetid: cbc01a3a-3b69-4ded-9c42-ecbf0fd0a00e
ms.openlocfilehash: e9efc207fe0ed49fecf30366d265019e7a3ee009
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50440528"
---
# <a name="namespaces-and-type-visibility-ccx-"></a>Ad alanları ve tür görünürlüğü (C + +/ CX)

Standart bir C++ yapı ilgili işlevleri türlerini gruplama ve kitaplıklarında ad çakışmalarını önleme için bir ad alanıdır. Windows çalışma zamanı tür sistemi, kendi kodunuzu de dahil olmak üzere, tüm ortak Windows çalışma zamanı türleri ad alanı kapsamında bir ad alanı içinde bildirilmelidir gerektirir. Genel kapsamda bildirilen veya başka bir sınıf içinde iç içe geçmiş genel türler, bir derleme zamanı hatasına neden olur.

.Winmd dosyası, kök ad alanı olan aynı ada sahip olmalıdır. Örneğin, yalnızca A.winmd veya A.B.winmd veya A.B.C.winmd adlı bir meta veri dosyasında tanımlanan A.B.C.MyClass adlı bir sınıf oluşturulabilir. Yürütülebilir dosya adını .winmd dosyası adı ile eşleşmesi için gerekli değildir.

## <a name="type-visibility"></a>Tür görünürlüğü

Windows çalışma zamanı türleri bir ad alanında — Standart C++ türlerinin aksine — özel veya genel erişilebilirliğine sahip olmalıdır. Varsayılan olarak, Erişilebilirlik özeldir. Genel bir türü için meta verileri görünür ve bu nedenle kullanılabilir uygulamalar ve bileşenlerin C++ dışındaki dillerde yazılmış olabilir. Genel olarak, görünür türler .NET dilleri veya JavaScript desteklenmeyen C++ diline özgü kavramları gösteremez çünkü görünebilir türler için kuralları görünmeyen türler için kuralları daha kısıtlayıcı.

> [!NOTE]
> Meta veriler, yalnızca .NET dilleri ile JavaScript çalışma zamanında kullanılır. Ne zaman bir C++ uygulama veya bileşen konuştuğu başka bir C++ uygulama veya bileşen — bu, tüm C++ programında yazılan Windows bileşenleri içerir — hiçbir meta veri çalışma zamanı tüketiminin gereklidir.

## <a name="member-accessibility-and-visibility"></a>Üye erişilebilirliği ve görünürlük

Genel erişilebilirlik olsa bile bir özel başvuru sınıfı arabirim veya temsilci, hiç üye meta verileri için gönderilir. Public ref sınıfları, kaynak kodunuzda kendi erişilebilirlik bağımsız olarak meta veri üyelerinde görünürlüğünü denetleyebilirsiniz. Standart C++ olduğu gibi en düşük öncelik ilkesini uygulayın; kesinlikle olmalıdır sürece üyelerinizin meta verilerinde görünür hale getirmez.

Hem meta veriler görünürlük ve kaynak kod erişilebilirlik denetlemek için aşağıdaki erişim değiştiriciler kullanın.

||||
|-|-|-|
|Değiştirici|Açıklama|Meta verileri yayılan?|
|private|Varsayılan erişilebilirlik. Standart C++ olduğu gibi aynı anlamına gelir.|Hayır|
|protected|Standart C++, uygulama veya bileşen hem meta veriler de olduğu gibi aynı anlamına gelir.|Evet|
|public|Standart C++ olduğu gibi aynı anlamına gelir.|Evet|
|`public protected` - veya - `protected public`|Meta veri, uygulama veya bileşen içinde ortak erişilebilirlik korumalı.|Evet|
|`protected private` veya `private protected`|Meta verilerde görünmez; uygulama veya bileşen erişilebilirlik korumalı.||
|`internal` veya `private public`|Üye uygulama veya bileşen içinde geneldir ancak meta verilerinde görünür değil.|Hayır|

## <a name="windows-runtime-namespaces"></a>Windows çalışma zamanı ad alanları

Windows API Windows içinde bildirilen türleri oluşur::\* ad alanları. Bu ad alanlarında, Windows için ayrılmıştır ve türleri kendisine eklenemez. İçinde **Nesne Tarayıcısı**, bu ad alanları Windows.winmd'i dosyasında görüntüleyebilirsiniz. Bu ad alanları hakkında daha fazla bilgi için bkz [Windows API](https://msdn.microsoft.com/library/windows/apps/br211377).

## <a name="ccx-namespaces"></a>C + +/ CX ad alanları

C + +/ CX Windows çalışma zamanı tür sistemi projeksiyon bir parçası olarak bu ad alanlarında belirli türlerini tanımlayın.

|||
|-|-|
|**Namespace**|**Açıklama**|
|default|Yerleşik sayısal ve char16 türleri içerir. Bu tür, her ad alanı kapsamında bulunan ve bir `using` deyimi gereklidir hiçbir zaman.|
|Platform|Gibi Windows çalışma zamanı türlerine karşılık gelen öncelikli olarak genel türler içeren `Array<T>`, `String`, `Guid`, ve `Boolean`. Ayrıca gibi özel yardımcı türleri içerir `Platform::Agile<T>` ve `Platform::Box<T>`.|
|Platform::Collections|Windows çalışma zamanı koleksiyon arabirimleri uygulayan somut koleksiyon sınıfları içeren `IVector`, `IMap`ve benzeri. Bu tür collection.h, platform.winmd değil, bir üstbilgi dosyasında tanımlanır.|
|Platform::details|Ortak tüketim için tasarlanmamıştır ve derleyici tarafından kullanılan türler içerir.|

## <a name="see-also"></a>Ayrıca Bkz.

[Tür Sistemi (C++/CX)](../cppcx/type-system-c-cx.md)
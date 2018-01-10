---
title: "Ad alanları ve tür görünürlüğü (C + +/ CX) | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cbc01a3a-3b69-4ded-9c42-ecbf0fd0a00e
caps.latest.revision: "13"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 03e86a7cbb36a0cfdf0ad2d32d625eae0102b25a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="namespaces-and-type-visibility-ccx-"></a>Ad alanları ve tür görünürlüğü (C + +/ CX)
Bir ad alanı bir standart C++ ilgili işlevleri türlerini gruplama için ve ad çakışmaları kitaplıklarında engellemek için yapıdır. Windows çalışma zamanı tür sistemi kendi kodunuzu de dahil, tüm genel Windows çalışma zamanı tür ad alanı kapsamında bir ad alanındaki bildirilmelidir gerektirir. Genel kapsamda bildirilen veya başka bir sınıf içinde iç içe geçmiş genel türler, derleme zamanı hataya neden olur.  
  
 Bir .winmd dosyası kök ad alanı var. aynı ada sahip olmalıdır. Örneğin, yalnızca A.winmd veya A.B.winmd veya A.B.C.winmd adlı bir meta veri dosyasında tanımlanırsa A.B.C.MyClass adlı bir sınıf oluşturulabilir. Yürütülebilir dosyanın adını .winmd dosya adı ile eşleşmesi için gerekli değildir.  
  
## <a name="type-visibility"></a>Tür görünürlüğü  
 Windows çalışma zamanı türü bir ad alanındaki — standart C++ türlerinin aksine — özel veya genel erişilebilirlik sahip. Varsayılan olarak, Erişilebilirlik özeldir. Yalnızca ortak bir türü meta verileri görünür durumda ve bu nedenle tüketilebilir uygulamaları ve bileşenleri C++ dışındaki dillerde yazılmış olabilir. .NET dillerinden veya JavaScript desteklenmez C++ özgü kavramları görünebilir türler gösteremez çünkü genel olarak, görünür türleri için görünür olmayan türleri için kurallarından daha kısıtlayıcı kurallardır.  
  
> [!NOTE]
>  Meta veriler yalnızca çalışma zamanında .NET dilleri ve JavaScript tarafından tüketilen. Ne zaman bir C++ uygulama veya bir bileşen Konuşmayı başka bir C++ uygulama veya bileşen — bu, tüm C++ ile yazılmış Windows bileşenlerini içerir — meta verilerin herhangi bir çalışma zamanı tüketim gereklidir.  
  
## <a name="member-accessibility-and-visibility"></a>Üye erişilebilirlik ve görünürlük  
 Ortak erişilebilirlik olsa bile hiçbir üye bir özel ref sınıfı arabirim veya temsilci, meta veriler için gösterilen. Ortak ref sınıflarda kaynak kodunuzda bağımsız olarak kendi erişilebilirlik meta verilerini üye görünürlüğünü kontrol edebilirsiniz. Standart C++ olduğu gibi en az ayrıcalık ilkesini uygulayın; kesinlikle olmalıdır sürece üyelerinizin meta verilerde görünür yapmayın.  
  
 Meta veri görünürlük ve kaynak kodu erişilebilirlik denetlemek için aşağıdaki erişim değiştiricileri kullanın.  
  
||||  
|-|-|-|  
|Değiştirici|Açıklama|Meta veriler için gösterilen?|  
|private|Varsayılan erişilebilirlik. Standart C++ olduğu gibi ile aynı anlamı.|Hayır|  
|protected|Standart C++, uygulama veya bileşen içinde hem meta verilerde olduğu gibi ile aynı anlamı.|Evet|  
|public|Standart C++ olduğu gibi ile aynı anlamı.|Evet|  
|`public protected`- veya -`protected public`|Erişilebilirlik meta verileri, uygulama veya bileşen içinde genel korumalı.|Evet|  
|`protected private`veya`private protected`|Meta verilerde görünmez; Erişilebilirlik uygulama veya bileşenin içinde korumalı.||  
|`internal`veya`private public`|Üye uygulama veya bileşen içinde genel olan, ancak meta verilerde görünür değil.|Hayır|  
  
## <a name="windows-runtime-namespaces"></a>Windows çalışma zamanı ad alanları  
 Windows API Windows belirtilen türlerine oluşur::\* ad alanları. Bu ad alanları Windows için ayrılmıştır ve türleri kendisine eklenemez. İçinde **Nesne Tarayıcısı**, bu ad alanları windows.winmd dosyasında görüntüleyebilirsiniz. Bu ad alanları hakkında daha fazla belgeler için bkz: [Windows API](http://msdn.microsoft.com/library/windows/apps/br211377).  
  
## <a name="ccx-namespaces"></a>C + +/ CX ad alanları  
 C + +/ CX Windows çalışma zamanı tür sistemi projeksiyon bir parçası olarak bu ad alanlarında belirli türlerini tanımlayın.  
  
|||  
|-|-|  
|**Namespace**|**Açıklama**|  
|default|Yerleşik sayısal ve char16 türler içerir. Her ad alanı kapsamda bu türleridir ve `using` deyimi gereklidir hiçbir zaman.|  
|Platform|Windows çalışma zamanı türleri gibi karşılık gelen öncelikle ortak türleri içeren `Array<T>`, `String`, `Guid`, ve `Boolean`. Ayrıca özel yardımcı türleri gibi içerir `Platform::Agile<T>` ve `Platform::Box<T>`.|  
|Platform::Collections|Windows çalışma zamanı koleksiyon arabirimleri uygulayan somut koleksiyon sınıfları içeren `IVector`, `IMap`ve benzeri. Bu tür bir üstbilgi dosyası platform.winmd içinde değil collection.h tanımlanır.|  
|Platform::details|Derleyici tarafından kullanılır ve ortak tüketim için düşünülmemiştir türlerini içerir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür Sistemi (C++/CX)](../cppcx/type-system-c-cx.md)
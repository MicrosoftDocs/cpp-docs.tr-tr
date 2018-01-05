---
title: "Kısmi sınıflar (C + +/ CX) | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69d93575-636c-4564-8cca-6dfba0c7e328
caps.latest.revision: "15"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e122f84bff2b815a00e50950b90230a9d50907a1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="partial-classes-ccx"></a>Kısmi sınıflar (C + +/ CX)
Bir parçalı sınıf içinde değişiklik bir sınıf tanımı ve otomatik kod oluşturma yazılım bir bölümünü senaryoları destekleyen bir yapıdır — Örneğin, XAML Tasarımcısı — aynı sınıf kodunda da değiştiriyor. Kısmi bir sınıf kullanarak kodunuzu üzerine yazılmasını Tasarımcı engelleyebilir. Visual Studio Proje `partial` değiştiricisi oluşturulan dosya otomatik olarak uygulanır.  
  
## <a name="syntax"></a>Sözdizimi  
 Bir parçalı sınıf tanımlamak için `partial` anahtar sözcüğü hemen önce ne normal sınıf tanımını Aksi durumda olacak, sınıf anahtarı. Bir anahtar sözcük gibi `partial ref class` boşluk karakterleri içeren bağlamsal bir anahtardır. Kısmi tanımları aşağıdaki yapılardan desteklenir.  
  
-   `class`veya`struct`  
  
-   `ref class`veya`ref struct`  
  
-   `value class`veya`value struct`  
  
-   `enum`veya`enum class`  
  
-   `ref interface`, `interface class`, `interface struct`, veya`__interface`  
  
-   `union`  
  
 Bu örnek, kısmi gösterir `ref class`:  
  
 [!code-cpp[cx_partial#01](../cppcx/codesnippet/CPP/partialclassexample/class1.h#01)]  
  
## <a name="contents"></a>İçindekiler  
 Bir parçalı sınıf tanımı tam sınıf tanımı, içerebilir herhangi bir şey içerebilir `partial` anahtar sözcüğü atlanmış. Bunun tek istisnası, bu temel sınıfları, veri üyeleri, üye işlevleri, numaralandırmalar, arkadaş bildirimleri ve öznitelikler gibi geçerli bir yapı içerir. Ve satır içi tanımları statik veri üyeleri izin verilir.  
  
 Tek özel durum sınıfı erişilebilirlik kullanılır. Örneğin, deyim `public partial class MyInvalidClass {/* ... */};` bir hatadır. Bir parçalı sınıf tanımında MyInvalidClass için kullanılan tüm erişim tanımlayıcıları için MyInvalidClass sonraki kısmi veya tam sınıf tanımında varsayılan erişilebilirlik etkilemez.  
  
 Aşağıdaki kod parçası erişilebilirlik gösterir. İlk kısmi sınıfında `Method1` kendi erişilebilirlik ortak olduğu için geneldir. İkinci kısmi sınıfında `Method2` varsayılan sınıf erişilebilirlik özel olduğundan özeldir.  
  
 [!code-cpp[cx_partial#02](../cppcx/codesnippet/CPP/partialclassexample/class1.h#02)]  
  
## <a name="declaration"></a>Bildirim  
 Kısmi bir gibi bir sınıf tanımını *MyClass* yalnızca MyClass bildirimini değil. Diğer bir deyişle, adı yalnızca tanıtır *MyClass*. *MyClass* boyutunu bilerek bir sınıf tanımı, örneğin, gerektiren bir şekilde kullanılamaz *MyClass* veya bir temel veya üyesi kullanarak *MyClass*. *MyClass* yalnızca derleyici kısmi olmayan tanımının karşılaştığında tanımlanacak kabul *MyClass*.  
  
 Aşağıdaki örnek, bir parçalı sınıf bildirimi davranışını gösterir. Bildirim #1 sonra *MyClass* ileriye dönük bildirimi yazılmış şekilde varsa kullanılabilir `ref class MyClass;`. Bir sınıfa ileriye dönük bildirimi olduğundan #2 bildirimi #1.Declaration #3 eşdeğerdir bildirimi geçerlidir. Ancak bildirim #4 geçersiz olduğundan  
  
 *MyClass* tam olarak tanımlı değil.  
  
 Bildirim #5 kullanmaz `partial` anahtar sözcüğü ve bildirimi tam olarak tanımlayan *MyClass*. Sonuç olarak, bildirim #6 geçerli değil.  
  
 [!code-cpp[Cx_partial#03](../cppcx/codesnippet/CPP/partialclassexample/class1.h#03)]  
  
## <a name="number-and-ordering"></a>Sayı ve sıralama  
 Her tam bir sınıf tanımını için sıfır veya daha çok parçalı sınıf tanımları olabilir.  
  
 Her bir sınıfın parçalı sınıf tanımını sözcüksel olarak bu sınıfın bir tam tanımını gelmelidir ancak sınıfının iletme bildirimlerden önce gerekmez. Sınıfının tam tanım ise, kısmi sınıf bildirimleri yalnızca iletme bildirimleri olabilir.  
  
 Tüm sınıfı anahtarlar gibi `class` ve `struct` eşleşmesi gerekir. Örneğin, bir hata koduna `partial class X {}; struct X {};`.  
  
 Aşağıdaki örnek, sayı ve sıralama gösterir. Sınıf zaten tanımlı olduğu için son kısmi bildirimi başarısız olur.  
  
 [!code-cpp[cx_partial#04](../cppcx/codesnippet/CPP/partialclassexample/class1.h#04)]  
  
## <a name="full-definition"></a>Tam tanımı  
 X tanımını tüm temel sınıfları, üyeleri ve sırada, bunlar karşılaştı ve kısmi sınıflarda tanımlanan belirli bir benzeri bildirilen sanki tam sınıfının tanımını X noktasında, aynı davranıştır. Diğer bir deyişle, kısmi sınıflar içeriğini tam sınıf tanımını noktasında yazılmıştır ve ad arama ve diğer dili kurallarını sınıfının tam tanımını noktasında uygulanır gibi ele alınmıştır gibi kısmi sınıflar içeriğini yerinde yazılmış  
  
 Aşağıdaki iki kod örnekleri aynı anlamı ve etkisi vardır. İlk örnek bir parçalı sınıf kullanır ve ikinci örnek değil.  
  
 [!code-cpp[cx_partial#05](../cppcx/codesnippet/CPP/partialclassexample/class1.h#05)]  
  
 [!code-cpp[cx_partial#06](../cppcx/codesnippet/CPP/partialclassexample/class1.h#06)]  
  
## <a name="templates"></a>Şablonlar  
 Kısmi bir sınıf bir şablonu olamaz.  
  
## <a name="restrictions"></a>Kısıtlamalar  
 Kısmi bir sınıf dışında bir çeviri birim yayılamaz.  
  
 `partial` Anahtar sözcüğü ile birlikte, yalnızca desteklenen `ref class` anahtar sözcüğü veya `value class` anahtar sözcüğü.  
  
### <a name="examples"></a>Örnekler  
 Aşağıdaki örnek tanımlar `Address` iki kod dosyaları arasında sınıfı. Tasarımcı değiştirir `Address.details.h` ve değişiklik `Address.h`. İlk dosya yalnızca sınıf tanımında kullanan `partial` anahtar sözcüğü.  
  
 [!code-cpp[cx_partial#07](../cppcx/codesnippet/CPP/partialclassexample/address.details.h#07)]  
  
 [!code-cpp[cx_partial#09](../cppcx/codesnippet/CPP/partialclassexample/address.h#09)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi](../cppcx/type-system-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)
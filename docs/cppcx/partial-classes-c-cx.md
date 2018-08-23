---
title: Kısmi sınıflar (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 69d93575-636c-4564-8cca-6dfba0c7e328
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd1d5f7559b88505929153ae1852fc42171e5208
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593032"
---
# <a name="partial-classes-ccx"></a>Kısmi sınıflar (C + +/ CX)
Kısmi bir sınıf içinde değiştirmekte bir sınıf tanımı ve otomatik kod oluşturma yazılım parçası senaryoları destekleyen bir yapıdır — Örneğin, XAML Tasarımcısı — aynı sınıftaki kod da değiştiriyor. Kısmi bir sınıf kullanarak kodunuzu silmelerini Tasarımcı engelleyebilirsiniz. Visual Studio projesinde `partial` değiştiricisi için oluşturulan dosya otomatik olarak uygulanır.  
  
## <a name="syntax"></a>Sözdizimi  
 Kısmi bir sınıf tanımlamak için `partial` ne normal sınıf tanımını Aksi durumda olacak, sınıf anahtarı hemen önce anahtar sözcüğü. Bir anahtar sözcüğü gibi `partial ref class` boşluk karakterleri içeren bir bağlamsal anahtar sözcük. Kısmi tanımlar, aşağıdaki yapılarında desteklenir.  
  
-   `class` veya `struct`  
  
-   `ref class` veya `ref struct`  
  
-   `value class` veya `value struct`  
  
-   `enum` veya `enum class`  
  
-   `ref interface`, `interface class`, `interface struct`, veya `__interface`  
  
-   `union`  
  
 Bu örnek, kısmi gösterir `ref class`:  
  
 [!code-cpp[cx_partial#01](../cppcx/codesnippet/CPP/partialclassexample/class1.h#01)]  
  
## <a name="contents"></a>İçindekiler  
 Kısmi sınıf tanımı, tam sınıf tanımını içerebilir herhangi bir şeyi içerebilir `partial` anahtar sözcüğü atlanmış. Bunun tek istisnası, bu temel sınıfları, veri üyeleri, üye işlevleri, numaralandırmalar, arkadaş bildirimleri ve öznitelikleri gibi geçerli bir yapısı içerir. Ve statik veri üyesi satır içi tanımları izin verilir.  
  
 Bir sınıf erişilebilirlik istisnadır. Örneğin, deyim `public partial class MyInvalidClass {/* ... */};` bir hatadır. Kısmi sınıf tanımında MyInvalidClass için kullanılan herhangi bir erişim belirticisi, bir sonraki kısmi veya tam sınıf tanımı içinde varsayılan erişilebilirlik için MyInvalidClass etkilemez.  
  
 Aşağıdaki kod parçası, Erişilebilirlik gösterir. İlk kısmi sınıftaki `Method1` erişilebilirliğini genel olduğu için geneldir. İkinci kısmi sınıftaki `Method2` varsayılan sınıf erişilebilirlik özel olduğu için özeldir.  
  
 [!code-cpp[cx_partial#02](../cppcx/codesnippet/CPP/partialclassexample/class1.h#02)]  
  
## <a name="declaration"></a>Bildirim  
 Kısmi gibi bir sınıf tanımlaması *MyClass* yalnızca bir MyClass bildirimidir. Diğer bir deyişle, adı yalnızca tanıtan *MyClass*. *MyClass* boyutunu bilmek bir sınıf tanımı, örneğin, gerektiren bir şekilde kullanılan *MyClass* veya bir taban veya üye kullanarak *MyClass*. *MyClass* yalnızca derleyicinin olmayan kısmi tanımını karşılaştığında tanımlanması kabul *MyClass*.  
  
 Aşağıdaki örnek, kısmi sınıf bildirimi davranışını gösterir. Sonra bildirimi #1 *MyClass* İleri dönük bildirimi yazılmışlar gibi kullanılabilir `ref class MyClass;`. Bir sınıf için İleri dönük bildiriminin olduğundan bildirimi #1.Declaration #3'için #2 eşdeğerdir bildirimi geçerli değil. Ancak #4 bildirimi geçersiz olduğundan  
  
 *MyClass* tam olarak tanımlı değil.  
  
 Bildirim #5 kullanmayan `partial` anahtar sözcüğü ve bildirimi tam olarak tanımlar *MyClass*. Sonuç olarak, #6 bildirimi geçerli değil.  
  
 [!code-cpp[Cx_partial#03](../cppcx/codesnippet/CPP/partialclassexample/class1.h#03)]  
  
## <a name="number-and-ordering"></a>Sayı ve sıralama  
 Her bir sınıf tam tanımı için sıfır veya daha fazla kısmi sınıf tanımları olabilir.  
  
 Her bir sınıfı kısmi sınıf tanımının söz konusu sınıfın bir tam tanımı sözcüksel olarak gelmelidir, ancak sınıf bildirimleri öncesinde gerekli değildir. Sınıfın tam tanımı yok ise, kısmi sınıf bildirimleri yalnızca bildirimleri olabilir.  
  
 Tüm sınıfı anahtarları gibi `class` ve `struct` eşleşmelidir. Örneğin, bir hata koduna olduğu `partial class X {}; struct X {};`.  
  
 Aşağıdaki örnek, sayı ve sıralama gösterir. Sınıf zaten tanımlı olduğundan son partial bildirimi başarısız olur.  
  
 [!code-cpp[cx_partial#04](../cppcx/codesnippet/CPP/partialclassexample/class1.h#04)]  
  
## <a name="full-definition"></a>Tam tanımı  
 X tanımını tüm temel sınıflar, üyeler ve sırada, bunlar karşılaştı ve kısmi sınıflarında tanımlanan belirli bir benzeri bildirilen gibi X sınıfının tam tanımını noktasında davranışı aynıdır. Diğer bir deyişle, parçalı sınıflar içeriğini sınıfının tam tanım noktasında yazılmış olan ve ad arama ve diğer dil kuralları sınıfının tam tanım noktasında uygulandığı gibi ele alınmıştır gibi kısmi sınıflar içeriği yerinde yazılmıştır  
  
 Aşağıdaki iki kod örnekleri, aynı anlamı ve etkili sahip. İlk örnek bir parçalı sınıf kullanır ve ikinci örnek değil.  
  
 [!code-cpp[cx_partial#05](../cppcx/codesnippet/CPP/partialclassexample/class1.h#05)]  
  
 [!code-cpp[cx_partial#06](../cppcx/codesnippet/CPP/partialclassexample/class1.h#06)]  
  
## <a name="templates"></a>Şablonlar  
 Kısmi bir sınıf, bir şablon olamaz.  
  
## <a name="restrictions"></a>Kısıtlamalar  
 Kısmi bir sınıf dışında bir çeviri birimi yayılamaz.  
  
 `partial` Anahtar sözcüğü, yalnızca birlikte içerisinde desteklendiği `ref class` anahtar sözcüğü veya `value class` anahtar sözcüğü.  
  
### <a name="examples"></a>Örnekler  
 Aşağıdaki örnek tanımlar `Address` iki kod dosyaları arasında sınıfı. Tasarımcı değiştirir `Address.details.h` ve değişiklik `Address.h`. İlk dosya yalnızca sınıf tanımında kullanan `partial` anahtar sözcüğü.  
  
 [!code-cpp[cx_partial#07](../cppcx/codesnippet/CPP/partialclassexample/address.details.h#07)]  
  
 [!code-cpp[cx_partial#09](../cppcx/codesnippet/CPP/partialclassexample/address.h#09)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi](../cppcx/type-system-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)
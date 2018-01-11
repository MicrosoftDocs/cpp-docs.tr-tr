---
title: noexcept (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: noexcept_cpp
dev_langs: C++
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5068c7cf010c128fd7954ddfd356f49158bf6f17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="noexcept-c"></a>noexcept (C++)
**C ++ 11:** bir işlev özel durumlar oluşturma belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
> *noexcept ifade*:  
> &nbsp;&nbsp;&nbsp;&nbsp;**noexcept**  
> &nbsp;&nbsp;&nbsp;&nbsp;**noexcept (** *sabit ifadesi* **)**  
  
### <a name="parameters"></a>Parametreler  
 *Sabit ifadesi*  
 Sabit bir ifade türü `bool` olası özel durum türleri kümesi boş olup olmadığını gösterir. Koşulsuz sürümü eşdeğerdir `noexcept(true)`.  
  
## <a name="remarks"></a>Açıklamalar  
 A *noexcept ifade* bir tür, *özel durum belirtimi*, sonek çıkar herhangi bir özel durum için bir özel durum işleyicisi tarafından eşleştirilmesini türleri kümesini temsil eden bir işlev bildirimi için bir işlev. Birli koşullu işleç `noexcept(` *constant_expression* `)` nerede *constant_expression* yeilds `true`ve kendi koşulsuz eş `noexcept`, bir işlev çıkabilirsiniz olası özel durum türleri kümesi boş olduğunu belirtin. Diğer bir deyişle, işlev hiçbir zaman bir özel durum oluşturur ve hiçbir zaman kapsamı dışında yayılması bir özel durum sağlar. İşleç `noexcept(` *constant_expression* `)` nerede *constant_expression* yeilds `false`, veya bir özel durum belirtimi (dışında için bir yıkıcı veya ayırmayı kaldırma işlevini), belirlenen işlevi çıkabilirsiniz olası özel durumların tüm türleri kümesi olduğunu gösterir.  
 
 Bir işlevi olarak işaretlemek `noexcept` yalnızca, doğrudan veya dolaylı olarak çağırır tüm işlevleri de varsa `noexcept` veya `const`. Derleyici her kod yolu en fazla Kabarcık özel durumlar için denetleme olmayan bir `noexcept` işlevi. Bir özel durum olarak işaretlenmiş bir işlev dış kapsamını çıkmak `noexcept`, [std::terminate](../standard-library/exception-functions.md#terminate) hemen çağrılır ve herhangi bir kapsam içinde nesne Yıkıcılar çağrılacak garantisi yoktur. Kullanım `noexcept` dinamik özel durum belirleyici yerine `throw`, hangi C ++ 11'de kullanım dışı ve daha sonra ve tam olarak Visual Studio'da uygulanmadı. Uyguladığınız önerilen `noexcept` hiçbir zaman bir özel durum çağrı yığınına yayılmaya sağlayan işlev. Bir işlev bildirilen zaman `noexcept`, birkaç farklı bağlamlarda daha verimli kodu oluşturmak derleyici sağlar.    
  
## <a name="example"></a>Örnek  
Bağımsız değişkeni kopyalar bir şablon işlevi bildirilen `noexcept` kopyalanan nesne düz eski veri türü (POD) koşuluyla. Bu tür bir işlevi şöyle bildirilen:  
  
```cpp  
#include <type_traits>  
  
template <typename T>  
T copy_object(const T& obj) noexcept(std::is_pod<T>)  
{  
   // ...   
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ özel durum işleme](../cpp/cpp-exception-handling.md) [özel durum belirtimleri (throw, noexcept)](../cpp/exception-specifications-throw-cpp.md)
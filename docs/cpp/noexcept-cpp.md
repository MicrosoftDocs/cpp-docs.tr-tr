---
title: noexcept (C++) | Microsoft Docs
ms.custom: ''
ms.date: 01/12/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- noexcept_cpp
dev_langs:
- C++
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8eb8e6900dc12e4f176daf63bb711198f5e41429
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939295"
---
# <a name="noexcept-c"></a>noexcept (C++)
**C ++ 11:** bir işlev özel durum oluşturma olasılığı olup olmadığını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
> *noexcept ifade*:  
> &nbsp;&nbsp;&nbsp;&nbsp;**noexcept**  
> &nbsp;&nbsp;&nbsp;&nbsp;**noexcept (** *sabit-ifade* **)**  
  
### <a name="parameters"></a>Parametreler  
 *constant-expression*  
 Sabit bir ifade türü **bool** olası özel durum türleri boş olup olmadığını gösterir. Koşulsuz sürümü eşdeğerdir `noexcept(true)`.  
  
## <a name="remarks"></a>Açıklamalar  
 A *noexcept ifade* bir tür, *özel durum belirtimi*, sonek çıkar herhangi bir özel durum için bir özel durum işleyicisi tarafından eşleştirilen türleri kümesini temsil eden bir işlev bildirimi için bir işlev. Koşullu işleç birli `noexcept(` *constant_expression* `)` burada *constant_expression* yeilds **true**ve onun koşulsuz eş anlamlı `noexcept`, bir işlev çıkabilirsiniz olası özel durum türleri boş olduğunu belirtin. Yani işlev hiçbir zaman bir özel durum oluşturur ve hiçbir zaman bir özel durum kapsamı dışında dağıtılmasını sağlar. İşleç `noexcept(` *constant_expression* `)` burada *constant_expression* yeilds **false**, veya bir özel durum belirtimi (dışındaki bir yok Edicisi veya ayırmayı kaldırma işlevi için), işlev çıkabilirsiniz olası özel durumları kümesini tüm türleri olduğunu gösterir.  
 
 Bir işlev olarak işaretlemek `noexcept` yalnızca, doğrudan veya dolaylı olarak çağrı yaptığı tüm işlevlerin Ayrıca, `noexcept` veya **const**. Derleyicinin tüm kod yolları kadar Kabarcık özel durumlar için denetleme değil bir `noexcept` işlevi. Bir özel durum dış kapsamını işaretli bir işlevden çıkış `noexcept`, [std::terminate](../standard-library/exception-functions.md#terminate) hemen çağrılır ve kapsamdaki tüm nesnelerin yıkıcıları çağrılacaktır garantisi yoktur. Kullanım `noexcept` dinamik özel durum tanımlayıcısı yerine `throw()`, artık kullanım dışı ve standart. Uyguladığınız önerilen `noexcept` hiçbir zaman bir özel durum çağrı yığınına yayılmaya sağlayan herhangi bir işlev. Bir işlev bildirilen zaman `noexcept`, birkaç farklı bağlamlardaki daha verimli kod oluşturma için derleyiciyi etkinleştirir. Daha fazla bilgi için [özel durum belirtimleri](exception-specifications-throw-cpp.md).   
  
## <a name="example"></a>Örnek  
Bağımsız değişkeni kopyalayan bir şablon işlevi bildirilen `noexcept` kopyalanan nesne düz eski veri türü (POD) koşuluyla. Böyle bir işlevi şu şekilde bildirilebilir:  
  
```cpp  
#include <type_traits>  
  
template <typename T>  
T copy_object(const T& obj) noexcept(std::is_pod<T>)  
{  
   // ...   
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ özel durum işleme](cpp-exception-handling.md) [özel durum belirtimleri (throw, noexcept)](exception-specifications-throw-cpp.md)
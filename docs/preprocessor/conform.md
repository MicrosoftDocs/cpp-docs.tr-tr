---
title: uygun | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- conform_CPP
- vc-pragma.conform
dev_langs:
- C++
helpviewer_keywords:
- conform pragma
- forScope conform pragma
- pragmas, conform
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c6204349731222df99683ddb20b2b2d827b3fcd
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42465418"
---
# <a name="conform"></a>conform
**C++ özgü**  
  
Çalışma zamanı davranışını belirtir [/ZC: forscope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) derleyici seçeneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma conform(name [, show ] [, on | off ] [ [, push | pop ] [, identifier ] ] )  
```  
  
### <a name="parameters"></a>Parametreler  
*Adı*  
Değiştirilecek derleyici seçeneğinin adı belirtir. Yalnızca geçerli *adı* olduğu `forScope`.  
  
*Göster* (isteğe bağlı)  
Geçerli ayarını neden *adı* (true veya false) derleme sırasında bir uyarı iletisi yoluyla görüntülenecek. Örneğin, `#pragma conform(forScope, show)`.  
  
*açık, kapalı*(isteğe bağlı)  
Ayarı *adı* için *üzerinde* sağlayan [/ZC: forscope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) derleyici seçeneği. Varsayılan değer *kapalı*.  
  
*anında iletme* (isteğe bağlı)  
Geçerli değerini gönderim *adı* iç derleyici yığınına sürükleyin. Belirtirseniz *tanımlayıcı*, belirtebileceğiniz *üzerinde* veya *kapalı* değerini *adı* da yığına itilecek. Örneğin, `#pragma conform(forScope, push, myname, on)`.  
  
*POP* (isteğe bağlı)  
Ayarlar *adı* değere iç derleyici yığınındaki ve ardından POP yığının üstünde. Tanımlayıcı belirtilirse *pop*, geri kayıtla buluncaya yığın POP *tanımlayıcısı*, hangi ayrıca POP; için geçerli değer *adı* içinde Yığında sonraki kaydı için yeni değer olur *adı*. Pop ile belirtirseniz bir *tanımlayıcı* olmayan yığında kaydındaki *pop* göz ardı edilir.  
  
*tanımlayıcı*(isteğe bağlı)  
İle dahil edilebilir bir *anında iletme* veya *pop* komutu. Varsa *tanımlayıcı* kullanılır, sonra bir *üzerinde* veya *kapalı* tanımlayıcısı de kullanılabilir.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// pragma_directive_conform.cpp  
// compile with: /W1  
// C4811 expected  
#pragma conform(forScope, show)  
#pragma conform(forScope, push, x, on)  
#pragma conform(forScope, push, x1, off)  
#pragma conform(forScope, push, x2, off)  
#pragma conform(forScope, push, x3, off)  
#pragma conform(forScope, show)  
#pragma conform(forScope, pop, x1)  
#pragma conform(forScope, show)  
  
int main() {}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
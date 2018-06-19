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
ms.openlocfilehash: b145225cfed3131b406d15827b589aed718d16bb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843749"
---
# <a name="conform"></a>conform
**C++ özel**  
  
 Çalışma zamanı davranışını belirtir [/ZC: forscope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) derleyici seçeneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma conform(name [, show ] [, on | off ] [ [, push | pop ] [, identifier ] ] )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Adı*  
 Değiştirilecek derleyici seçeneği adını belirtir. Yalnızca geçerli *adı* olan `forScope`.  
  
 **Göster** (isteğe bağlı)  
 Geçerli ayarını neden *adı* (true veya false) derleme sırasında yoluyla bir uyarı iletisi görüntülenecek. Örneğin, `#pragma conform(forScope, show)`.  
  
 **açık, kapalı**(isteğe bağlı)  
 Ayarı *adı* için **üzerinde** sağlayan [/ZC: forscope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) derleyici seçeneği. Varsayılan değer **devre dışı**.  
  
 **anında iletme** (isteğe bağlı)  
 Geçerli değeri iter *adı* derleyici iç yığına. Belirtirseniz *tanımlayıcısı*, belirleyebileceğiniz **üzerinde** veya **kapalı** değerini *adı* yığına edilmesini. Örneğin, `#pragma conform(forScope, push, myname, on)`.  
  
 **POP** (isteğe bağlı)  
 Değerini ayarlar *adı* derleyici iç yığını ve ardından POP yığın üstündeki değerine. Tanımlayıcı belirtilirse **pop**, geri kayıtla bulana kadar yığın Sil'i *tanımlayıcısı*, hangi ayrıca Sil'i; için geçerli değer *adı* içinde Yığında sonraki kaydı için yeni değer haline *adı*. Pop ile belirtirseniz bir *tanımlayıcısı* olmayan yığında kaydındaki **pop** göz ardı edilir.  
  
 *tanımlayıcı*(isteğe bağlı)  
 İle dahil edilebilir bir **itme** veya **pop** komutu. Varsa *tanımlayıcısı* kullanılır, sonra bir **üzerinde** veya **kapalı** belirticisi de kullanılabilir.  
  
## <a name="example"></a>Örnek  
  
```  
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
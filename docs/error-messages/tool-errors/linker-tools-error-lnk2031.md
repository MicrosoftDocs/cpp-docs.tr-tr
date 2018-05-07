---
title: Bağlayıcı araçları hatası LNK2031 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2031
dev_langs:
- C++
helpviewer_keywords:
- LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 179702b3e162ad9f22fd887d60c5a5c2d0bc8559
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2031"></a>Bağlayıcı Araçları Hatası LNK2031
p/Invoke "function_declaration" decorated_name için; oluşturulamıyor Meta veriler eksik çağırma  
  
 Yerel bir işleve saf görüntüsüne alınmaya çalışılırken örtük çağırma kurallarını yerel ve saf derlemeler arasında farklı olduğunu unutmayın. Saf görüntüleri hakkında daha fazla bilgi için bkz: [saf ve doğrulanabilen kod (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
 Bu kod örneği, çağırma olduğu örtük olarak dışarı aktarılan, yerel, işlevi içeren bir bileşen oluşturur [__cdecl](../../cpp/cdecl.md).  
  
```  
// LNK2031.cpp  
// compile with: /LD  
extern "C" {  
   __declspec(dllexport) int func() { return 3; }  
};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, yerel işlevi tüketir saf bir istemci oluşturur. Ancak, çağırma altında **/CLR: pure** olan [__clrcall](../../cpp/clrcall.md). Aşağıdaki örnek LNK2031 oluşturur.  
  
```  
// LNK2031_b.cpp  
// compile with: /clr:pure LNK2031.lib  
// LNK2031 expected  
extern "C" int func();  
  
int main() {  
   return func();  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, saf görüntü yerel işlevden tüketen gösterilmektedir. Açık Not **__cdecl** arama kuralı tanımlayıcısı.  
  
```  
// LNK2031_c.cpp  
// compile with: /clr:pure LNK2031.lib  
extern "C" int __cdecl func();  
  
int main() {  
   return func();  
}  
```
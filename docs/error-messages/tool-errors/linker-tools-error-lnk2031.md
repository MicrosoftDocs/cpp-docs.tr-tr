---
title: "Bağlayıcı araçları hatası LNK2031 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2031
dev_langs: C++
helpviewer_keywords: LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a519b4241c9ffabaeeb387cc8e4997125d57781
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
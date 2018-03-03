---
title: "Derleyici Hatası C2813 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C2813
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3cc6ac0e287894dc2202814c55dac37569650f5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2813"></a>Derleyici Hatası C2813
\#içeri aktarma ile /MP desteklenmiyor  
  
 Bir derleyici komut belirtirseniz C2813 yayılan **/MP** derleyici seçeneği ve derleme ve bir veya daha fazla dosya iki veya daha fazla dosyaları içeren[#import](../../preprocessor/hash-import-directive-cpp.md) önişlemci yönergesi. [#İmport](../../preprocessor/hash-import-directive-cpp.md) yönergesi belirtilen tür kitaplığı'nda türlerinden C++ sınıfları oluşturur ve ardından bu sınıfların iki üst bilgi dosyaları yazar. [#İmport](../../preprocessor/hash-import-directive-cpp.md) yönergesi birden çok derleme biriminden aynı tür kitaplığı içe aktarırsanız, aynı anda aynı başlık dosyaları yazmak çalıştıklarında bu birimleri çakıştığından desteklenmiyor.  
  
 Bu derleyici hatası ve **/MP** derleyici seçeneği Visual Studio 2008'de yenidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2813 oluşturur. Komut satırında "ile derleme:" açıklama gösterir kullanılacak derleyici **/MP** ve **/c** birkaç dosyalarını derlemek için derleyici seçenekleri. Dosya en az birini içeren [#import](../../preprocessor/hash-import-directive-cpp.md) yönergesi. Bu örnekte test amacıyla iki kere aynı dosya kullanırız.  
  
```  
// C2813.cpp  
// compile with: /MP /c C2813.cpp C2813.cpp  
#import "C:\windows\system32\stdole2.tlb"   // C2813  
int main()   
{  
}  
```
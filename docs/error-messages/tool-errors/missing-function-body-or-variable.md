---
title: "Eksik işlev gövdesi veya değişken | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 356d0f0a71feccee953a0b1bd7dc54bc64a0e233
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="missing-function-body-or-variable"></a>Eksik İşlev Gövdesi veya Değişken
Yalnızca bir işlev prototipi derleyici hatasız devam edebilirsiniz, ancak işlev kodu veya ayrılmış değişken alanı olmadığından bağlayıcı bir adresi çağrısı çözümlenemiyor. Bağlayıcı çözülmelidir işlevi çağrısı oluşturana kadar bu hata görmezsiniz.  
  
## <a name="example"></a>Örnek  
 Exists işlevi düşünmek derleyici prototip izin verdiğinden ana işlev çağrısında LNK2019 neden olur.  Bağlayıcı olmayan olduğunu bulur.  
  
```  
// LNK2019_MFBV.cpp  
// LNK2019 expected  
void DoSomething(void);  
int main() {  
   DoSomething();  
}  
```  
  
## <a name="example"></a>Örnek  
 C++'da bir sınıf ve yalnızca bir prototip için belirli bir işlev uygulaması sınıf tanımında eklediğinizden emin olun. Üstbilgi dosyası dışında sınıfı tanımlıyorsanız, sınıf adı işlevi önce eklediğinizden emin olun (`Classname::memberfunction`).  
  
```  
// LNK2019_MFBV_2.cpp  
// LNK2019 expected  
struct A {  
   static void Test();  
};  
  
// Should be void A::Test() {}  
void Test() {}  
  
int main() {  
   A AObject;  
   AObject.Test();  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı Araçları Hatası LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
---
title: Eksik işlev gövdesi veya değişken | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54e2b8c5831eb6d487cf530df1b733b73580cbb8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
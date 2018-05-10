---
title: (C/C++) kullanım dışı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.deprecated
- deprecated_CPP
dev_langs:
- C++
helpviewer_keywords:
- deprecated pragma
- pragmas, deprecated
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2280d5245292625bfc29815475eaca63d4d500bd
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="deprecated-cc"></a>deprecated (C/C++)
**Kullanım dışı** gösteren bir işlev, tür veya başka bir tanımlayıcı artık bir gelecekte desteklenebilir olduğunu pragma sağlar serbest bırakma veya artık kullanılmalıdır.  
> [!NOTE]
> C ++ 14 hakkında bilgi için `[[deprecated]]` özniteliği ve ne zaman, kullanılacağı hakkında yönergeler vs Microsoft declspec veya pragma özniteliği için bkz: [C++ Standart öznitelikleri](../cpp/attributes.md) özniteliği.
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma deprecated( identifier1 [,identifier2, ...] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Derleyici tarafından belirtilen tanımlayıcı karşılaştığında bir **kullanım dışı** pragma, derleyici uyarısı sorunları [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md).   
  
 Makro adları alanı onaylanamadı. Yerleştir makrosu genişletme yoksa teklifleri makrosu adlarında meydana gelir.  
  
 Çünkü **kullanım dışı** pragma tüm eşleşen tanımlayıcılarını çalışır ve imzalar dikkate almaz, aşırı yüklenen işlevler belirli sürümlerini onaysız kılınmadan için en iyi seçenek değildir. Kapsam içine getirilene eşleşen hiçbir işlev adı uyarı tetikler.

  C ++ 14 kullanmanızı öneririz `[[deprecated]]` yerine, mümkün olduğunda, öznitelik **kullanım dışı** pragması. Microsoft'a özgü [__declspec(deprecated)](../cpp/deprecated-cpp.md) bildirimi değiştiricisi değil de birçok durumda daha iyi bir seçim **kullanım dışı** pragması. `[[deprecated]]` Özniteliği ve `__declspec(deprecated)` değiştiricisi aşırı yüklenmiş işlevlerin belirli formları için kullanım dışı durum belirtmenize olanak tanır. Tanılama uyarı yalnızca belirli bir aşırı yüklenmiş işlev başvuruları öznitelik görüntülenir veya değiştiricisi uygular.  
  
## <a name="example"></a>Örnek  
  
```  
// pragma_directive_deprecated.cpp  
// compile with: /W3  
#include <stdio.h>  
void func1(void) {  
}  
  
void func2(void) {  
}  
  
int main() {  
   func1();  
   func2();  
   #pragma deprecated(func1, func2)  
   func1();   // C4995  
   func2();   // C4995  
}  
```  
  
 Aşağıdaki örnek, bir sınıf alanı onaylanamadı gösterilmektedir:  
  
```  
// pragma_directive_deprecated2.cpp  
// compile with: /W3  
#pragma deprecated(X)  
class X {  // C4995  
public:  
   void f(){}  
};  
  
int main() {  
   X x;   // C4995  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
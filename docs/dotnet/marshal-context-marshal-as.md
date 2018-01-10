---
title: marshal_context::marshal_as | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- marshal_context::marshal_as
- marshal_context.marshal_as
- msclr.interop.marshal_context.marshal_as
- msclr::interop::marshal_context::marshal_as
dev_langs: C++
helpviewer_keywords: marshal_context class [C++], operations
ms.assetid: 24a1afee-51c0-497c-948c-f77fe43635c8
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e56e225d136fb02445eeeb398937adc075f2dae7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="marshalcontextmarshalas"></a>marshal_context::marshal_as
Yönetilen ve yerel veri türü arasında dönüştürme için belirli bir veri nesnesi üzerinde sıralama gerçekleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
To_Type marshal_as<To_Type>(  
   From_Type input   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`input`  
 İçin hazırlamak istediğiniz değeri bir `To_Type` değişkeni.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Türünde bir değişken `To_Type` diğer bir deyişle dönüştürülmüş değeri `input`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev bir özel veri nesnesi hazırlama gerçekleştirir. Bu işlev yalnızca tabloda belirtildiği dönüşümleri kullanın [, genel bakış hazırlama c++](../dotnet/overview-of-marshaling-in-cpp.md).  
  
 Desteklenmeyen veri türleri çifti sıralamakta çalışırsanız `marshal_as` bir hata oluşturur [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) derleme zamanında. Daha fazla bilgi için bu hata ile sağlanan iletisini okuyun. `C4996` Hata birden fazla yalnızca kullanım dışı işlevleri için oluşturulabilir. Bu hatayı üreten iki koşul desteklenmeyen veri türleri çifti hazırlarken ve kullanmayı deneyen `marshal_as` bir bağlam gerektiren bir dönüştürme için.  
  
 Hazırlama kitaplığını birkaç üstbilgi dosyaları içerir. Herhangi bir dönüştürmeye yalnızca bir dosya gerektirir, ancak diğer dönüştürmeleri için gerekiyorsa, ek dosyalar içerebilir. Tabloda `Marshaling Overview in C++` hangi hazırlama dosyasını her dönüştürme için eklenmesi gerektiğini gösterir.  
  
## <a name="example"></a>Örnek  
 Bu örnek, gelen hazırlama için bir bağlam oluşturur bir `System::String` için bir `const char *` değişken türü. Dönüştürülen veri bağlamı siler satırından sonra geçerli olmayacak.  
  
```  
// marshal_context_test.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   marshal_context^ context = gcnew marshal_context();  
   String^ message = gcnew String("Test String to Marshal");  
   const char* result;  
   result = context->marshal_as<const char*>( message );  
   delete context;  
   return 0;  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi dosyası:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, veya \<msclr\marshal_atl.h >  
  
 **Namespace:** msclr::interop  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++'da hazırlamaya genel bakış](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_as](../dotnet/marshal-as.md)   
 [marshal_context Class](../dotnet/marshal-context-class.md)
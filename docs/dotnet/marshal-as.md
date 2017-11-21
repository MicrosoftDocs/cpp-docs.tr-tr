---
title: marshal_as | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- marshal_as
- msclr.interop.marshal_as
- msclr::interop::marshal_as
dev_langs: C++
helpviewer_keywords: marshal_as template [C++]
ms.assetid: 2ed717da-2b11-41e5-981d-47d251771989
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e9d91cf582e9ffc6e6236e27d82c0e516214d650
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="marshalas"></a>marshal_as
Bu yöntem, yerel ve yönetilen ortamlar arasında veri dönüştürür.  
  
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
 Bu yöntem, yerel ve yönetilen türleri arasında verileri dönüştürmek için basitleştirilmiş bir yoludur. Hangi veri türlerinin desteklendiğini belirlemek için bkz: [, genel bakış hazırlama c++](../dotnet/overview-of-marshaling-in-cpp.md). Bazı veri dönüşümleri bir bağlam gerektirir. Bu veri türlerini kullanarak dönüştürebilirsiniz [marshal_context sınıfı](../dotnet/marshal-context-class.md).  
  
 Desteklenmeyen veri türleri çifti sıralamakta çalışırsanız `marshal_as` bir hata oluşturur [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) derleme zamanında. Daha fazla bilgi için bu hata ile sağlanan iletisini okuyun. `C4996` Hata birden fazla yalnızca kullanım dışı işlevleri için oluşturulabilir. Desteklenmeyen veri türleri çifti sıralamakta bunun bir örneği çalışıyor.  
  
 Hazırlama kitaplığını birkaç üstbilgi dosyaları içerir. Herhangi bir dönüştürmeye yalnızca bir dosya gerektirir, ancak diğer dönüştürmeleri için gerekiyorsa, ek dosyalar içerebilir. Tabloda hangi dönüşümleri hangi dosyalarıyla ilişkili olduğunu görmek için Ara `Marshaling Overview`. Yapmak istediğiniz hangi dönüştürülmesi ne olursa olsun, ad alanı her zaman etkin gereksinimdir.  
  
## <a name="example"></a>Örnek  
 Bu örnek gelen sıralar bir `const char*` için bir `System::String` değişken türü.  
  
```  
// marshal_as_test.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   const char* message = "Test String to Marshal";  
   String^ result;  
   result = marshal_as<String^>( message );  
   return 0;  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi dosyası:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, veya \<msclr\marshal_atl.h >  
  
 **Namespace:** msclr::interop  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++'da hazırlamaya genel bakış](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_context sınıfı](../dotnet/marshal-context-class.md)
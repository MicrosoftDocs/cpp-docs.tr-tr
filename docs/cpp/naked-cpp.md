---
title: naked (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- naked_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], naked
- naked __declspec keyword
ms.assetid: 69723241-05e1-439b-868e-20a83a16ab6d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1057754b5c98086de42daedd5e7aab70656eba69
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948024"
---
# <a name="naked-c"></a>naked (C++)
**Microsoft'a özgü**  
  
 Bildirilen işlevler **naked** özniteliği, derleyici giriş ve sonuç kodu olmadan kod oluşturur. Satır içi derleyici kodunu kullanarak kendi giriş/sonuç kodu dizilerinizi yazmak için bu özelliği kullanabilirsiniz. Çıplak işlevler, özellikle sanal cihaz sürücülerinin yazılmasında yararlıdır.  Unutmayın **naked** özniteliği yalnızca x86 ve ARM geçerli olduğundan ve mevcut değildir [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)].  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__declspec(naked) declarator  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Çünkü **naked** özniteliği yalnızca bir işlev tanımı için geçerlidir ve bir tür değiştiricisi değil, naked işlevleri, genişletilmiş öznitelik söz dizimi kullanmalıdır ve [__declspec](../cpp/declspec.md) anahtar sözcüğü.  
  

 İşlev ayrıca ile işaretlenmiş olsa bile derleyici, çıplak özniteliği ile işaretlenmiş bir işlevin satır içi işlev oluşturulamıyor [__forceinline](inline-functions-cpp.md) anahtar sözcüğü.  

  
 Varsa derleyici bir hata verir **naked** öznitelik, bir üye olmayan yöntem tanımının dışında her şey için uygulanır.  
  
## <a name="examples"></a>Örnekler  
 Bu kod, bir işlev ile tanımlar **naked** özniteliği:  
  
```  
__declspec( naked ) int func( formal_parameters ) {}  
```  
  
 Veya alternatif olarak:  
  
```  
#define Naked __declspec( naked )  
Naked int func( formal_parameters ) {}  
```  
  
 **Naked** özniteliği, yalnızca işlevin giriş ve sonuç dizileri için derleyicinin kod oluşturma yapısını etkiler. Bu tür işlevleri çağırmak için oluşturulan kodu etkilemez. Bu nedenle, **naked** özniteliği işlev türünün bir parçası değil değerlendirilir ve işlev işaretçileri olamaz **naked** özniteliği. Ayrıca, **naked** özniteliği veri tanımına uygulanamaz. Örneğin, bu kod örneği, bir hata oluşturur:  
  
```  
__declspec( naked ) int i;  
// Error--naked attribute not permitted on data declarations.  
```  
  
 **Naked** özniteliği yalnızca işlevin tanımıyla ilgilidir ve işlevin prototipinde belirtilemez. Örneğin, bu bildirim, bir derleyici hatası oluşturur:  
  
```  
__declspec( naked ) int func();  // Error--naked attribute not permitted on function declarations  
```  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Naked İşlevi Çağrıları](../cpp/naked-function-calls.md)
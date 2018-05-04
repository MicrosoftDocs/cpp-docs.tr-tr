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
ms.openlocfilehash: 84e172c24bbb87f9243a4c0de25a98c90e043acc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="naked-c"></a>naked (C++)
**Microsoft özel**  
  
 İle bildirilen işlevler için `naked` özniteliği, derleyici giriş ve bitiş kodu olmadan kod oluşturur. Satır içi derleyici kodunu kullanarak kendi giriş/sonuç kodu dizilerinizi yazmak için bu özelliği kullanabilirsiniz. Çıplak işlevler, özellikle sanal cihaz sürücülerinin yazılmasında yararlıdır.  Unutmayın `naked` özniteliği yalnızca x86 ve ARM üzerinde geçerli olduğundan ve mevcut değildir [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)].  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__declspec(naked) declarator  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Çünkü `naked` özniteliği yalnızca bir işlev tanımı için geçerlidir ve bir tür değiştiricisi değil, naked işlevleri genişletilmiş öznitelik sözdizimini kullanmanız gerekir ve [__declspec](../cpp/declspec.md) anahtar sözcüğü.  
  

 İşlevi de ile işaretlenmiş olsa bile derleyici naked özniteliğiyle işaretlenmiş bir işlev için satır içi işlev üretilemiyor [__forceinline](inline-functions-cpp.md) anahtar sözcüğü.  

  
 Derleyici, bir hata verir `naked` özniteliği bir üyesi olmayan yöntem tanımını dışında her şey için uygulanır.  
  
## <a name="examples"></a>Örnekler  
 Bu kod, bir işlev tanımlar `naked` özniteliği:  
  
```  
__declspec( naked ) int func( formal_parameters ) {}  
```  
  
 Veya alternatif olarak:  
  
```  
#define Naked __declspec( naked )  
Naked int func( formal_parameters ) {}  
```  
  
 `naked` özniteliği, yalnızca işlevin giriş ve sonuç dizileri için derleyicinin kod oluşturma yapısını etkiler. Bu tür işlevleri çağırmak için oluşturulan kodu etkilemez. Bu nedenle, `naked` özniteliği işlev türünün bir parçası olarak kabul edilmez ve işlev işaretçileri `naked` özniteliğine sahip olamaz. Ayrıca, `naked` özniteliği veri tanımına uygulanamaz. Örneğin, bu kod örneği, bir hata oluşturur:  
  
```  
__declspec( naked ) int i;       // Error--naked attribute not  
                                 // permitted on data declarations.  
```  
  
 `naked` özniteliği, yalnızca işlevin tanımıyla ilgilidir ve işlevin prototipinde belirtilemez. Örneğin, bu bildirim bir derleyici hatası oluşturur:  
  
```  
__declspec( naked ) int func();  // Error--naked attribute not   
                                 // permitted on function declarations  
```  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Naked İşlevi Çağrıları](../cpp/naked-function-calls.md)
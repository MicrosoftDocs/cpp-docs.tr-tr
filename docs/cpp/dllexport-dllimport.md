---
title: dllexport, dllimport | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- dllimport_cpp
- dllexport_cpp
dev_langs:
- C++
helpviewer_keywords:
- dllexport __declspec keyword
- __declspec keyword [C++], dllexport
- dllimport __declspec keyword
- __declspec keyword [C++], dllimport
ms.assetid: ff95b645-ef55-4e72-b848-df44657b3208
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d4e5b98b5541d1dc5f4a94c9611668a9ea8d787a
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="dllexport-dllimport"></a>dllexport, dllimport
**Microsoft Specific**  
  
 `dllexport` Ve **dllimport** depolama sınıfı öznitelikler C ve C++ dilleri için Microsoft'a özgü uzantılar bağlıdır. Ya da DLL'den işlevleri, veri ve nesneleri almak ve vermek için bunları kullanabilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
   __declspec( dllimport ) declarator  
   __declspec( dllexport ) declarator  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu öznitelikler DLL'nin arabirimi yürütülebilir dosya veya başka bir DLL olabilir, istemciye açıkça tanımlayın. İşlevleri bildirme `dllexport` bir modül-tanımlama (.def) dosyası en az dışarı aktarılan işlevleri'nin belirtimine göre ortadan kaldırır. `dllexport` Özniteliği değiştirir `__export` anahtar sözcüğü.  
  
 Bir sınıf declspec(dllexport) işaretlenmişse sınıf şablonlarının sınıf hiyerarşisindeki tüm özelleştirmeleri örtük olarak declspec(dllexport) işaretlenir. Bu sınıf şablonları açıkça örneği ve sınıf'ın üyeleri tanımlanmalıdır anlamına gelir.  
  
 `dllexport`bir işlevi olarak düzenlenmiş adıyla işlevi sunar. İçin C++ işlevlerini, bu ad bozma içerir. C işlevlerini veya olarak bildirilen işlevler için `extern "C"`, bu arama kuralına göre platforma özgü decoration içerir. C/C++ kod ad düzenleme hakkında daha fazla bilgi için bkz: [donatılmış adları](../build/reference/decorated-names.md). Ad düzenlemesi dışarı aktarılan C işlevlerini ya da C++ uygulanan `extern "C"` kullanarak işlevleri `__cdecl` çağırma.  
  
 Ve bir ad vermek için bir dışarı aktarma bölümünde ve adını tanımlayan bir modül tanımlama (.def) dosyası kullanarak bağlayabilirsiniz. Daha fazla bilgi için bkz: [dışarı](../build/reference/exports.md). Ve bir ad vermek için başka bir yolu bir `#pragma comment(linker, "/export:alias=decorated_name")` kaynak kodundaki yönergesi.  
  
 Ne zaman bildirdiğiniz `dllexport` veya **dllimport**, kullanmalısınız [öznitelik sözdizimi Genişletilmiş](../cpp/declspec.md) ve `__declspec` anahtar sözcüğü.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// Example of the dllimport and dllexport class attributes  
__declspec( dllimport ) int i;  
__declspec( dllexport ) void func();  
```  
  
 Alternatif olarak, kodunuzu daha okunabilir hale getirmek için makro tanımlarını kullanabilirsiniz:  
  
```cpp  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllExport void func();  
DllExport int i = 10;  
DllImport int j;  
DllExport int n;  
```  
  
 Daha fazla bilgi için bkz.:  
  
-   [Tanımlar ve bildirimler](../cpp/definitions-and-declarations-cpp.md)  
  
-   [dllexport ve dllimport ile Satır İçi C++ İşlevlerini Tanımlama](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)  
  
-   [Genel Kurallar ve Sınırlamalar](../cpp/general-rules-and-limitations.md)  
  
-   [C++ Sınıflarında dllimport ve dllexport Kullanma](../cpp/using-dllimport-and-dllexport-in-cpp-classes.md)  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)
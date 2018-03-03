---
title: "Geçersiz kılma tanımlayıcıları (C++ bileşen uzantıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- override specifiers, Visual C++
- override specifiers
ms.assetid: 155bbf6f-4722-4654-afb1-9cb52af799fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7937e0eec53a800c7bcef2842310af368949bcca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="override-specifiers--c-component-extensions"></a>Geçersiz Kılma Tanımlayıcıları (C++ Bileşen Uzantıları)
*Geçersiz kılma tanımlayıcıları* devralınan türleri üyeleri türetilmiş türlerde yapılandıran ve nasıl devralınan türlerini değiştirebilirsiniz.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 **Açıklamalar**  
  
 Geçersiz kılma tanımlayıcıları hakkında daha fazla bilgi için bkz:  
  
-   [abstract](../windows/abstract-cpp-component-extensions.md)  
  
-   [Yeni (vtable'de yeni yuva)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
-   [override](../windows/override-cpp-component-extensions.md)  
  
-   [sealed](../windows/sealed-cpp-component-extensions.md)  
  
-   [Geçersiz kılma tanımlayıcıları ve yerel derleme](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)  
  
 `abstract`ve `sealed` da, bunlar geçersiz kılma tanımlayıcıları olarak hareket değil türü bildirimlerinde geçerlidir.  
  
 Açıkça temel sınıf işlevleri geçersiz kılma hakkında daha fazla bilgi için bkz: [açık geçersiz kılmalar](../windows/explicit-overrides-cpp-component-extensions.md).  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 (Yalnızca Windows çalışma zamanı için geçerli hiçbir açıklamalar için bu dil özelliği vardır.)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı  
 (Yalnızca ortak dil çalışma zamanı için geçerli hiçbir açıklamalar için bu dil özelliği vardır.)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)
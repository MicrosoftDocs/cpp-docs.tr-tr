---
title: "Geçersiz kılma tanımlayıcıları (C++ bileşen uzantıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- override specifiers, Visual C++
- override specifiers
ms.assetid: 155bbf6f-4722-4654-afb1-9cb52af799fb
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c314e224bbbc9b7d232ee9e2cb9bbc20ec8ead71
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="override-specifiers--c-component-extensions"></a>Geçersiz Kılma Tanımlayıcıları (C++ Bileşen Uzantıları)
*Geçersiz kılma tanımlayıcıları* devralınan türleri üyeleri türetilmiş türlerde yapılandıran ve nasıl devralınan türlerini değiştirebilirsiniz.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 **Açıklamalar**  
  
 Geçersiz kılma tanımlayıcıları hakkında daha fazla bilgi için bkz:  
  
-   [Özet](../windows/abstract-cpp-component-extensions.md)  
  
-   [Yeni (vtable'de yeni yuva)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
-   [geçersiz kılma](../windows/override-cpp-component-extensions.md)  
  
-   [korumalı](../windows/sealed-cpp-component-extensions.md)  
  
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
 [Çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md)
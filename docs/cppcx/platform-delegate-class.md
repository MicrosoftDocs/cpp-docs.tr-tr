---
title: "Platform::delegate sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/Platform::Delegate
dev_langs: C++
helpviewer_keywords: Platform::Delegate Class
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a95dad9833bcf1bebe9d9f74eceb05efcfa8ce0f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="platformdelegate-class"></a>Platform::delegate sınıfı
İşlev nesnesi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
public delegate void delegate_name();  
```  
  
### <a name="members"></a>Üyeler  
 Temsilci sınıfı GetHashCode(), Equals() sahiptir ve ToString() yöntemleri türetilen [Platform::Object sınıfı](../cppcx/platform-object-class.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanmak [temsilci](../windows/delegate-cpp-component-extensions.md) temsilciler; oluşturmak için anahtar sözcüğü Platform::Delegate açıkça kullanmayın. Daha fazla bilgi için bkz: [Temsilciler](../cppcx/delegates-c-cx.md). Örneği nasıl oluşturulacağı ve bir temsilci kullanmak için bkz: [C++'da Windows çalışma zamanı bileşenleri oluşturma](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Desteklenen en düşük sunucu:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Meta veriler:** platform.winmd  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
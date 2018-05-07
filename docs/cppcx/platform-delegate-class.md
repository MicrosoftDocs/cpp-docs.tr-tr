---
title: Platform::delegate sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Delegate
dev_langs:
- C++
helpviewer_keywords:
- Platform::Delegate Class
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 679a868cac536aad541d770433fe1407fc5d08d1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
 Kullanmak [temsilci](../windows/delegate-cpp-component-extensions.md) temsilciler; oluşturmak için anahtar sözcüğü Platform::Delegate açıkça kullanmayın. Daha fazla bilgi için bkz: [Temsilciler](../cppcx/delegates-c-cx.md). Örneği nasıl oluşturulacağı ve bir temsilci kullanmak için bkz: [C++'da Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Desteklenen en düşük sunucu:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Meta veriler:** platform.winmd  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
---
title: Derleyici Uyarısı C4687 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4687
dev_langs:
- C++
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ad45c4bb2456b3bc23114233c084bbad1551e27
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272727"
---
# <a name="compiler-warning-c4687"></a>Derleyici Uyarısı C4687
'class': korumalı bir Özet sınıf bir arabirim 'arabirimi' uygulayamaz  
  
 Korumalı, soyut bir tür genellikle yalnızca statik üye işlevleri yararlıdır.  
  
 Daha fazla bilgi için bkz: [soyut](../../windows/abstract-cpp-component-extensions.md)ve [korumalı](../../windows/sealed-cpp-component-extensions.md).  
  
 C4687 hata olarak varsayılan olarak verilir. İle C4687 gizleyebilirsiniz [uyarı](../../preprocessor/warning.md) pragması. Bir korumalı, soyut türü bir arabirim uygulamak istediğinize eminseniz C4687 gizleyebilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4687 oluşturur.  
  
```  
// C4687.cpp  
// compile with: /clr /c  
interface class A {};  
  
ref struct B sealed abstract : A {};   // C4687  
ref struct C sealed : A {};   // OK  
ref struct D abstract : A {};   // OK  
```
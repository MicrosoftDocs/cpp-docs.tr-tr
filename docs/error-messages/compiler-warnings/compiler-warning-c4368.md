---
title: Derleyici Uyarısı C4368 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4368
dev_langs:
- C++
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3a7e53c979a3b13bde205a4546c486061a17110
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270502"
---
# <a name="compiler-warning-c4368"></a>Derleyici Uyarısı C4368
Yönetilen 'type' üyesi olarak 'üyesi' tanımlanamıyor: karışık türleri desteklenmiyor  
  
 Bir CLR türü bir yerel veri üyesi eklenemiyor.  
  
 Bununla birlikte, yerel bir tür için bir işaretçi bildirme ve yaşam süresi oluşturucusu ve yıkıcı yönetilen sınıfınızın sonlandırıcıyı denetleyebilirsiniz. Daha fazla bilgi için bkz: [yok ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
 Bu uyarı, hata olarak her zaman görüntülenir. Kullanım [uyarı](../../preprocessor/warning.md) C4368 devre dışı bırakmak için pragması.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4368 oluşturur.  
  
```  
// C4368.cpp  
// compile with: /clr /c  
struct N {};  
ref struct O {};  
ref struct R {  
    R() : m_p( new N ) {}  
    ~R() { delete m_p; }  
  
   property N prop;   // C4368  
   int i[10];   // C4368  
  
   property O ^ prop2;   // OK  
   N * m_p;   // OK  
};  
```
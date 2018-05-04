---
title: __super | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __super_cpp
dev_langs:
- C++
helpviewer_keywords:
- __super keyword [C++]
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91ce48232884d1ab242ed52f82f614de058a2f91
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="super"></a>__super
**Microsoft özel**  
  
 Geçersiz kılma bir işlev için bir temel sınıf uygulamasını çağırma açıkça durum olanak tanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
__super::  
member_function  
();  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Tüm erişilebilir taban sınıf yöntemlerini aşırı yükleme çözümü aşamasında olarak kabul edilir ve en iyi eşleşmeyi sağlayan işlev çağrılır adrestir.  
  
 `__super` yalnızca bir üye işlev gövdesi içinde bulunabilir.  
  
 `__super` kullanarak bir kullanılamaz bildirimi. Bkz: [bildirimi kullanarak](../cpp/using-declaration.md) daha fazla bilgi için.  
  
 Girişiyle [öznitelikleri](../windows/cpp-attributes-reference.md) kod ekleme, kodunuzu tanımadığınız, ancak adları çağırmak istediğiniz yöntemleri içeren bir veya daha fazla temel sınıfları içerebilir.  
  
## <a name="example"></a>Örnek  
  
```  
// deriv_super.cpp  
// compile with: /c  
struct B1 {  
   void mf(int) {}  
};  
  
struct B2 {  
   void mf(short) {}  
  
   void mf(char) {}  
};  
  
struct D : B1, B2 {  
   void mf(short) {  
      __super::mf(1);   // Calls B1::mf(int)  
      __super::mf('s');   // Calls B2::mf(char)  
   }  
};  
```  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)
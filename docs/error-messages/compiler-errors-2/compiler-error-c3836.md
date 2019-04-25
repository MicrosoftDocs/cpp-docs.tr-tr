---
title: Derleyici Hatası C3836
ms.date: 11/04/2016
f1_keywords:
- C3836
helpviewer_keywords:
- C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
ms.openlocfilehash: 33860273db07894a9a4d15ba6d578598a18819ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208063"
---
# <a name="compiler-error-c3836"></a>Derleyici Hatası C3836

statik Oluşturucu üye başlatıcı listesi olmasına izin verilmiyor

Yönetilen bir sınıf üyesi başlatma listesi olan bir statik oluşturucu olamaz. Statik sınıf oluşturucuları başlatma statik veri üyeleri başlatma, sınıf için ortak dil çalışma zamanı tarafından çağrılır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3836 oluşturur:

```
// C3836a.cpp
// compile with: /clr
ref class M
{
   static int s_i;

public:
   static M() :  s_i(1234)   // C3836, delete initializer to resolve
   {
   }
};

int main()
{
}
```

---
title: Statik Const Int bağlantısı değişmez değer artık | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- literal attribute [C++]
- constants, declaring
- integral constant expressions
ms.assetid: d2a5e3d2-ffb0-4b61-8114-bec5993a1195
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c51853274b061ba290ff90993f45ccdf3375349b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431300"
---
# <a name="static-const-int-linkage-is-no-longer-literal"></a>Statik Const Int Bağlantısı Artık Değişebilir Değerdir

Bir sabit bir sınıf üyesinin bildirimi, C++ için Visual C++ için Yönetilen Uzantılar'dan değişti.

Ancak `static const` integral üyeleri hala desteklenmektedir, kendi bağlantı özniteliği değişmiştir. Önceki bağlantı özniteliği artık sabit tamsayı üyesi olarak yürütülür. Örneğin, aşağıdaki uzantılar yönetilen sınıf göz önünde bulundurun:

```
public __gc class Constants {
public:
   static const int LOG_DEBUG = 4;
};
```

Bu, alanın (Not değişmez değer özniteliğinin) için aşağıdaki temel alınan CIL öznitelikleri oluşturur:

```
.field public static literal int32
modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)
```

Bu yeni sözdiziminde derlenmeye devam eder ancak:

```
public ref class Constants {
public:
   static const int LOG_DEBUG = 4;
};
```

artık değişmez değer özniteliğinin yayar ve bu nedenle sabit olarak CLR çalışma zamanı tarafından görüntülenen değil:

```
.field public static int32 modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)
```

Aynı diller arası değişmez değer özniteliğine sahip olmak için bildirimi değiştirilmelidir yeni desteklenen `literal` gösterildiği gibi veri üyesi

```
public ref class Constants {
public:
   literal int LOG_DEBUG = 4;
};
```

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfta veya Arabirimde Üye Bildirimleri (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
[değişmez değer](../windows/literal-cpp-component-extensions.md)
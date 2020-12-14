---
description: "Şu konuda daha fazla bilgi edinin: nasıl yapılır: yerel DLL 'i genel derleme önbelleğine ekleme"
title: "Nasıl yapılır: Yerel DLL'i Genel Derleme Önbelleğine Ekleme"
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], native
- GAC (global assembly cache), loading native DLLs
- native DLLs [C++]
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
ms.openlocfilehash: 267bc2f08fdd40da03b71222c48786ab7cc150fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335409"
---
# <a name="how-to-add-native-dll-to-global-assembly-cache"></a>Nasıl yapılır: Yerel DLL'i Genel Derleme Önbelleğine Ekleme

Genel derleme önbelleğine yerel bir DLL (COM değil) yerleştirebilirsiniz.

## <a name="example"></a>Örnek

**/Assemblylinkresource** , bir DERLEMEYE yerel dll eklemenize olanak sağlar.

Daha fazla bilgi için bkz. [/Assemblylinkresource (.NET Framework kaynağına bağlantı)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md).

```
/ASSEMBLYLINKRESOURCE:MyComponent.dll
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

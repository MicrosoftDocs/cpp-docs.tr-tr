---
title: "Nasıl yapılır: Yerel DLL'i genel derleme önbelleğine ekleme"
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], native
- GAC (global assembly cache), loading native DLLs
- native DLLs [C++]
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
ms.openlocfilehash: b4b886dfef3185c1b3084ed02abcef1ad2630c11
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57746493"
---
# <a name="how-to-add-native-dll-to-global-assembly-cache"></a>Nasıl yapılır: Yerel DLL'i genel derleme önbelleğine ekleme

Genel derleme önbelleğine yerel bir DLL (COM değil) koyabilirsiniz.

## <a name="example"></a>Örnek

**/ ASSEMBLYLINKRESOURCE** yerel bir DLL derlemede katıştırmak olanak tanır.

Daha fazla bilgi için [/assemblylınkresource (.NET Framework kaynağına bağlantı)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md).

```
/ASSEMBLYLINKRESOURCE:MyComponent.dll
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

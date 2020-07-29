---
title: DLL İçeri ve Dışarı Aktarma İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], importing
- dllimport attribute [C++], storage-class attribute
- DLL exports [C++]
- declaring functions, with dllexport and dllimport
- extended storage-class attributes
- dllexport attribute [C++], storage-class attribute
ms.assetid: 08d164b9-770a-4e14-afeb-c6f21d9e33e4
ms.openlocfilehash: 753a51fa8e2c87b77a54e5e93522e5f11585b610
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87200081"
---
# <a name="dll-import-and-export-functions"></a>DLL İçeri ve Dışarı Aktarma İşlevleri

**Microsoft'a Özgü**

Bu konuyla ilgili en kapsamlı ve güncel bilgiler [dllexport, dllimport](../cpp/dllexport-dllimport.md)içinde bulunabilir.

**`dllimport`** Ve `dllexport` depolama sınıfı değiştiricileri, C diline yönelik Microsoft 'a özgü uzantılardır. Bu değiştiriciler, DLL arabirimini istemciye (yürütülebilir dosya veya başka bir DLL) açık olarak tanımlar. İşlevlerin `dllexport` olarak bildirilmesi, modül tanım (.DEF) dosyasına yönelik gereksinimi ortadan kaldırır. Ayrıca, **`dllimport`** ve `dllexport` değiştiricilerini veri ve nesneler ile de kullanabilirsiniz.

**`dllimport`** Ve `dllexport` depolama sınıfı değiştiricileri, **`__declspec`** Aşağıdaki örnekte gösterildiği gibi genişletilmiş öznitelik sözdizimi anahtar sözcüğüyle birlikte kullanılmalıdır:

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllExport void func();
DllExport int i = 10;
DllExport int j;
DllExport int n;
```

Genişletilmiş depolama sınıfı değiştiricilerin sözdizimi hakkında belirli bilgiler için bkz. [genişletilmiş depolama sınıfı öznitelikleri](../c-language/c-extended-storage-class-attributes.md).

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C Işlev tanımları](../c-language/c-function-definitions.md)

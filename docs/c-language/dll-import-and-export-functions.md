---
description: ': DLL Içeri ve dışarı aktarma Işlevleri hakkında daha fazla bilgi'
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
ms.openlocfilehash: 9f734d4415b473717ad8cd7c94213f1beaff9dc8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213936"
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

Genişletilmiş depolama sınıfı değiştiricilerin sözdizimi hakkında belirli bilgiler için bkz. [genişletilmiş Storage-Class öznitelikleri](../c-language/c-extended-storage-class-attributes.md).

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C Işlev tanımları](../c-language/c-function-definitions.md)

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
ms.openlocfilehash: 8d703045773e4d2c320eaef2aa80c4ce74d23472
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62234253"
---
# <a name="dll-import-and-export-functions"></a>DLL İçeri ve Dışarı Aktarma İşlevleri

**Microsoft'a Özgü**

Bu konuyla ilgili en kapsamlı ve güncel bilgiler [dllexport, dllimport](../cpp/dllexport-dllimport.md)içinde bulunabilir.

**DllImport** ve `dllexport` depolama sınıfı değiştiricileri, C diline yönelik Microsoft 'a özgü uzantılardır. Bu değiştiriciler, DLL arabirimini istemciye (yürütülebilir dosya veya başka bir DLL) açık olarak tanımlar. İşlevlerin `dllexport` olarak bildirilmesi, modül tanım (.DEF) dosyasına yönelik gereksinimi ortadan kaldırır. Ayrıca, veri ve nesneler **dllimport** ile dllimport `dllexport` ve değiştiricilerini de kullanabilirsiniz.

Aşağıdaki **dllimport** örnekte gösterildiği `dllexport` gibi, DllImport ve depolama sınıfı değiştiricileri genişletilmiş öznitelik sözdizimi anahtar sözcüğüyle `__declspec`kullanılmalıdır:

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

[C İşlev Tanımları](../c-language/c-function-definitions.md)

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

**Microsoft'a özgü**

Bu konuyla ilgili en eksiksiz ve güncel bilgiler bulunabilir [dllexport, dllimport](../cpp/dllexport-dllimport.md).

**Dllimport** ve `dllexport` depolama sınıfı değiştiricileri C diline yönelik Microsoft'a özgü genişletmelerdir olan. Bu değiştiriciler, DLL arabirimini istemciye (yürütülebilir dosya veya başka bir DLL) açık olarak tanımlar. İşlevlerin `dllexport` olarak bildirilmesi, modül tanım (.DEF) dosyasına yönelik gereksinimi ortadan kaldırır. Ayrıca **dllimport** ve `dllexport` değiştiricilerini veri ve nesneleri.

**Dllimport** ve `dllexport` genişletilmiş öznitelik sözdizimi anahtar sözcüğü ile depolama sınıfı değiştiricilere kullanılan `__declspec`, bu örnekte gösterildiği gibi:

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllExport void func();
DllExport int i = 10;
DllExport int j;
DllExport int n;
```

Genişletilmiş depolama sınıfı değiştiricilere ilişkin sözdizimi hakkında ayrıntılı bilgi için bkz: [genişletilmiş depolama sınıfı öznitelikleri](../c-language/c-extended-storage-class-attributes.md).

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C İşlev Tanımları](../c-language/c-function-definitions.md)

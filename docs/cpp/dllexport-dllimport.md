---
title: dllexport, dllimport
ms.date: 11/04/2016
f1_keywords:
- dllimport_cpp
- dllexport_cpp
helpviewer_keywords:
- dllexport __declspec keyword
- __declspec keyword [C++], dllexport
- dllimport __declspec keyword
- __declspec keyword [C++], dllimport
ms.assetid: ff95b645-ef55-4e72-b848-df44657b3208
ms.openlocfilehash: 2ae284172828ed63b6499475df108c28aecb32ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525963"
---
# <a name="dllexport-dllimport"></a>dllexport, dllimport

**Microsoft'a özgü**

**Dllexport** ve **dllimport** depolama sınıfı öznitelikleri olan C ve C++ dilleri için Microsoft'a özgü uzantılardır. İşlevleri, verileri ve nesneleri için veya bir DLL içeri ve dışarı aktarmak kullanabilirsiniz.

## <a name="syntax"></a>Sözdizimi

```
   __declspec( dllimport ) declarator
   __declspec( dllexport ) declarator
```

## <a name="remarks"></a>Açıklamalar

Bu öznitelikler, DLL'nin arabirimini yürütülebilir dosya veya başka bir DLL olabilir, istemciye açıkça tanımlayın. İşlevleri bildirme **dllexport** dışarı aktarılan işlevlerin belirtimi açısından en az bir modül-tanımlama (.def) dosyası ihtiyacını ortadan kaldırır. **Dllexport** özniteliği değiştirir **__export** anahtar sözcüğü.

Bir sınıf declspec(dllexport) olarak, sınıf hiyerarşisindeki sınıf şablonlarının tüm uzmanlıkları örtük olarak declspec(dllexport) işaretlenir. Bunun anlamı, sınıf şablonlarının açıkça oluşturulduğu ve sınıf üyelerinin tanımlanması gerekir.

**dllexport** işlevi fonksiyonu düzenlenmiş adıyla gösterir. C++ işlevleri için ad değiştirmeyi içerir. C işlevleri veya olarak bildirilen işlevler için `extern "C"`, bu çağrı standardına göre platforma özgü düzenlemeler içerir. C/C++ kodundaki ad düzenleme hakkında daha fazla bilgi için bkz: [düzenlenmiş adlar](../build/reference/decorated-names.md). Hiçbir ad düzenlemesi dışarı aktarılan C işlevleri veya C++ için uygulanan `extern "C"` kullanan işlevler `__cdecl` çağırma kuralı.

Tamamlanmamış bir ad vermek için bir EXPORTS bölümünde düzenlenmemiş adını tanımlayan bir modül tanımlama (.def) dosyası kullanarak bağlayabilirsiniz. Daha fazla bilgi için [dışarı AKTARMALARI](../build/reference/exports.md). Tamamlanmamış bir ad vermek için başka bir yolu bir `#pragma comment(linker, "/export:alias=decorated_name")` kaynak kodunda yönergesi.

Bildirdiğinizde **dllexport** veya **dllimport**, kullanmanız gereken [genişletilmiş öznitelik sözdizimi](../cpp/declspec.md) ve **__declspec** anahtar sözcüğü.

## <a name="example"></a>Örnek

```cpp
// Example of the dllimport and dllexport class attributes
__declspec( dllimport ) int i;
__declspec( dllexport ) void func();
```

Alternatif olarak, kodunuzu daha okunabilir hale getirmek için makro tanımlarını kullanabilirsiniz:

```cpp
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllExport void func();
DllExport int i = 10;
DllImport int j;
DllExport int n;
```

Daha fazla bilgi için bkz.:

- [Tanımlar ve Bildirimler](../cpp/definitions-and-declarations-cpp.md)

- [dllexport ve dllimport ile Satır İçi C++ İşlevlerini Tanımlama](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)

- [Genel Kurallar ve Sınırlamalar](../cpp/general-rules-and-limitations.md)

- [C++ Sınıflarında dllimport ve dllexport Kullanma](../cpp/using-dllimport-and-dllexport-in-cpp-classes.md)

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
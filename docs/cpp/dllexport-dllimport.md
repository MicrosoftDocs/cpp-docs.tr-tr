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
ms.openlocfilehash: f03c945375cbe8c399e604e12f070b5a63d316f7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221659"
---
# <a name="dllexport-dllimport"></a>dllexport, dllimport

**Microsoft'a Özgü**

**`dllexport`** Ve **`dllimport`** depolama sınıfı öznitelikleri, C ve C++ dillerine yönelik Microsoft 'a özgü uzantılardır. Bunları, bir DLL 'ye veya DLL 'den işlevleri, verileri ve nesneleri içeri ve dışarı aktarmak için kullanabilirsiniz.

## <a name="syntax"></a>Sözdizimi

```
   __declspec( dllimport ) declarator
   __declspec( dllexport ) declarator
```

## <a name="remarks"></a>Açıklamalar

Bu öznitelikler,, çalıştırılabilir dosya veya başka bir DLL olabilen istemcisinin istemcisinin arabirimini açıkça tanımlar. İşlevleri bildirmek **`dllexport`** , en azından, aktarılmış işlevlerin belirtimine göre modül tanım (. def) dosyası gereksinimini ortadan kaldırır. **`dllexport`** Özniteliği **__export** anahtar sözcüğünün yerini alır.

Bir sınıf declspec (dllexport) olarak işaretlenmişse, sınıf hiyerarşisindeki sınıf şablonlarının herhangi bir uzmanlığını dolaylı olarak declspec (dllexport) olarak işaretlenir. Bu, sınıf şablonlarının açıkça örneklendiği ve sınıfın üyelerinin tanımlanması gerektiği anlamına gelir.

**`dllexport`** bir işlevin işlevi, kendisini düzenlenmiş adıyla gösterir. C++ işlevleri için, bu ad değiştirmeyi içerir. Olarak belirtilen C işlevleri veya işlevleri için `extern "C"` , bu, çağırma kuralına bağlı olan platforma özgü dekoratı içerir. C/C++ kodunda ad dekorasyonu hakkında daha fazla bilgi için bkz. [düzenlenmiş adlar](../build/reference/decorated-names.md). Çağıran kuralı kullanarak, içe aktarılmış C işlevlerine veya C++ işlevlerine hiçbir ad dekorat, uygulanmaz `extern "C"` **`__cdecl`** .

Açıklanmamalıdır bir adı dışarı aktarmak için, dışarı aktarmalar bölümünde, açıklanarak adı tanımlayan bir modül tanımı (. def) dosyası kullanarak bağlantı oluşturabilirsiniz. Daha fazla bilgi için bkz. [dışarı aktarmalar](../build/reference/exports.md). Açıklanmamalıdır bir adı dışa aktarmanın başka bir yolu `#pragma comment(linker, "/export:alias=decorated_name")` da kaynak kodunda bir yönerge kullanmaktır.

**`dllexport`** Veya bildirdiğinizde **`dllimport`** , [genişletilmiş öznitelik sözdizimini](../cpp/declspec.md) ve **`__declspec`** anahtar sözcüğünü kullanmanız gerekir.

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

Daha fazla bilgi için bkz.

- [Tanımlar ve bildirimler](../cpp/definitions-and-declarations-cpp.md)

- [Dllexport ve dllimport ile satır Içi C++ Işlevlerini tanımlama](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)

- [Genel kurallar ve sınırlamalar](../cpp/general-rules-and-limitations.md)

- [C++ sınıflarında dllimport ve dllexport kullanma](../cpp/using-dllimport-and-dllexport-in-cpp-classes.md)

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)

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
ms.openlocfilehash: 0a8d90770552b8b9ab9169378289108d91811216
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189461"
---
# <a name="dllexport-dllimport"></a>dllexport, dllimport

**Microsoft 'a özgü**

**Dllexport** ve **dllimport** depolama sınıfı öznitelikleri, C ve C++ dillerin Microsoft 'a özgü uzantılarıdır. Bunları, bir DLL 'ye veya DLL 'den işlevleri, verileri ve nesneleri içeri ve dışarı aktarmak için kullanabilirsiniz.

## <a name="syntax"></a>Sözdizimi

```
   __declspec( dllimport ) declarator
   __declspec( dllexport ) declarator
```

## <a name="remarks"></a>Açıklamalar

Bu öznitelikler,, çalıştırılabilir dosya veya başka bir DLL olabilen istemcisinin istemcisinin arabirimini açıkça tanımlar. İşlevleri **dllexport** olarak bildirmek, en azından, bir modül tanımı (. def) dosyası gereksinimini, en azından, dışarıya aktarılmış işlevlerin belirtimine göre ortadan kaldırır. **Dllexport** özniteliği **__export** anahtar sözcüğünün yerini alır.

Bir sınıf declspec (dllexport) olarak işaretlenmişse, sınıf hiyerarşisindeki sınıf şablonlarının herhangi bir uzmanlığını dolaylı olarak declspec (dllexport) olarak işaretlenir. Bu, sınıf şablonlarının açıkça örneklendiği ve sınıfın üyelerinin tanımlanması gerektiği anlamına gelir.

bir işlevin **dllexport** işlevi, kendisini düzenlenmiş adıyla gösterir. İşlevler C++ için, bu ad değiştirmeyi içerir. `extern "C"`olarak belirtilen C işlevleri veya işlevleri için, bu, çağırma kuralına göre platforma özgü dekoratı içerir. C/C++ Code 'da ad dekorasyonu hakkında daha fazla bilgi için bkz. [düzenlenmiş adlar](../build/reference/decorated-names.md). `__cdecl` çağırma kuralını kullanarak, dışarıya aktarılmış C işlevlerine veya C++ `extern "C"` işlevlere hiçbir ad düzenlemesi uygulanmaz.

Açıklanmamalıdır bir adı dışarı aktarmak için, dışarı aktarmalar bölümünde, açıklanarak adı tanımlayan bir modül tanımı (. def) dosyası kullanarak bağlantı oluşturabilirsiniz. Daha fazla bilgi için bkz. [dışarı aktarmalar](../build/reference/exports.md). Açıklanmamalıdır bir adı dışa aktarmanın başka bir yolu da kaynak kodda `#pragma comment(linker, "/export:alias=decorated_name")` yönergesini kullanmaktır.

**Dllexport** veya **dllimport**bildirdiğinizde, [genişletilmiş öznitelik sözdizimini](../cpp/declspec.md) ve **__declspec** anahtar sözcüğünü kullanmanız gerekir.

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

- [Tanımlar ve Bildirimler](../cpp/definitions-and-declarations-cpp.md)

- [dllexport ve dllimport ile Satır İçi C++ İşlevlerini Tanımlama](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)

- [Genel Kurallar ve Sınırlamalar](../cpp/general-rules-and-limitations.md)

- [C++ Sınıflarında dllimport ve dllexport Kullanma](../cpp/using-dllimport-and-dllexport-in-cpp-classes.md)

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)

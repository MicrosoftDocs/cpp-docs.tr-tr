---
title: __stdcall
ms.date: 10/10/2018
f1_keywords:
- __stdcall_cpp
- __stdcall
- _stdcall
helpviewer_keywords:
- __stdcall keyword [C++]
ms.assetid: e212594b-1827-4d07-9527-7d412b300df8
ms.openlocfilehash: 85d1b29fddece741aa94364bb6edfdf3b973faaf
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213183"
---
# <a name="__stdcall"></a>__stdcall

**`__stdcall`** Çağırma kuralı Win32 API işlevlerini çağırmak için kullanılır. Çağrılan yığını temizler, bu nedenle derleyici `vararg` işlevleri yapar **`__cdecl`** . Bu çağırma kuralını kullanan işlevler, bir işlev prototipi gerektirir. **`__stdcall`** Değiştirici, Microsoft 'a özgüdür.

## <a name="syntax"></a>Sözdizimi

> *dönüş türü* **`__stdcall`** *işlev adı*[ **`(`** *bağımsız değişken-listesi* **`)`** ]

## <a name="remarks"></a>Açıklamalar

Aşağıdaki liste bu çağırma kuralının uygulamasını gösterir.

|Öğe|Uygulama|
|-------------|--------------------|
|Bağımsız değişken geçirme sırası|Sağdan sola.|
|Bağımsız değişken geçirme kuralı|Bir işaretçi veya başvuru türü geçirilmemişse değere göre.|
|Yığın bakımı sorumluluğu|Çağrılan işlev, kendi bağımsız değişkenlerini yığından çıkarır.|
|Ad düzenleme kuralı|Ada bir alt çizgi ( `_` ) ön eki eklenir. Adından sonra gelen işareti ( `@` ) ve ardından bağımsız değişken listesindeki bayt sayısı (ondalık olarak) gelir. Bu nedenle, olarak belirtilen işlev `int func( int a, double b )` Şu şekilde tasarlanmıştır:`_func@12`|
|Durum çevirisi kuralları|Hiçbiri|

[/Gz](../build/reference/gd-gr-gv-gz-calling-convention.md) derleyici seçeneği, **`__stdcall`** farklı bir çağırma kuralıyla açıkça bildirilmeyen tüm işlevler için belirtir.

Önceki sürümlerle uyumluluk için, **`_stdcall`** **`__stdcall`** derleyici seçeneği [ `/Za` \( dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) ' ın belirtildiği durumlar için bir eş anlamlı olur.

**`__stdcall`** Değiştirici döndürme değerleri kullanılarak belirtilen işlevler, kullanılarak belirtilen işlevlerle aynı şekilde [`__cdecl`](../cpp/cdecl.md) .

ARM ve x64 işlemcilerde, **`__stdcall`** derleyici tarafından kabul edilir ve yok sayılır; ARM ve x64 mimarilerinde, kurala göre, bağımsız değişkenler mümkün olduğunda kayıtlara geçirilir ve sonraki bağımsız değişkenler yığına geçirilir.

Statik olmayan sınıf işlevleri için, işlev satır dışı olarak tanımlandıysa çağırma kuralı değiştiricinin satır dışı tanımda belirtilmesi gerekmez. Diğer bir deyişle, statik olmayan üye sınıfı yöntemler için tanım noktasında bildirim sırasında belirtilen çağırma kuralı kabul edilir. Bu sınıf tanımı verildiğinde,

```cpp
struct CMyClass {
   void __stdcall mymethod();
};
```

this

```cpp
void CMyClass::mymethod() { return; }
```

Buna eşdeğerdir

```cpp
void __stdcall CMyClass::mymethod() { return; }
```

## <a name="example"></a>Örnek

Aşağıdaki örnekte, **`__stdcall`** `WINAPI` bir standart çağrı olarak işlenen tüm işlev türlerinde sonuçların kullanılması gerekir:

```cpp
// Example of the __stdcall keyword
#define WINAPI __stdcall
// Example of the __stdcall keyword on function pointer
typedef BOOL (__stdcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);
```

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız değişken geçirme ve adlandırma kuralları](../cpp/argument-passing-and-naming-conventions.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)

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
ms.openlocfilehash: b9efac6f729a78db945ff3bd9ab16ebe315b7a5a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560647"
---
# <a name="stdcall"></a>__stdcall

**Microsoft'a özgü**

**__Stdcall** çağırma kuralı Win32 API işlevleri çağırmak için kullanılır. Aranan, yığını temizler, derleyici yapsak `vararg` işlevleri **__cdecl**. Bu çağrı kuralını kullanan işlevler bir işlev prototipi gerektirir.

## <a name="syntax"></a>Sözdizimi

> *dönüş türü*  **\_ \_stdcall** *işlevi adı*[**(** *bağımsız değişken listesi* **)** ]

## <a name="remarks"></a>Açıklamalar

Aşağıdaki liste bu çağırma kuralının uygulamasını gösterir.

|Öğe|Uygulama|
|-------------|--------------------|
|Bağımsız değişken geçirme sırası|Sağdan sola.|
|Bağımsız değişken geçirme kuralı|Değer bir işaretçi veya başvuru türü geçirilmezse.|
|Yığın bakımı sorumluluğu|Çağırılan işlev, yığından bağımsız kendi değişkenlerini yığından.|
|Ad düzenleme kuralı|Bir alt çizgi (_) adın önekidir. Adın ardından at işareti (@) bağımsız değişken listesinde (ondalık) bayt sayısı ardından. Bu nedenle, bildirilen işlev `int func( int a, double b )` şu şekilde sunulur: `_func@12`|
|Durum çevirisi kuralları|Yok.|

[/Gz](../build/reference/gd-gr-gv-gz-calling-convention.md) derleyici seçeneğini belirten **__stdcall** farklı bir çağırma kuralı açıkça bildirilmeyen tüm işlevler için.

Önceki sürümlerle uyumluluk için **_stdcall** eşanlamlıdır **__stdcall** sürece derleyici seçeneği [/Za \(dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md) olduğu Belirtilen.

Kullanılarak bildirilen işlevlerle **__stdcall** değiştirici dönüş değerleri kullanılarak bildirilen işlevlerle aynı şekilde [__cdecl](../cpp/cdecl.md).

ARM ve x64 işlemciler **__stdcall** kabul edilir ve derleyici tarafından; ARM ve x64 mimarileri, yoksayıldı. kural olarak, bağımsız değişkenler mümkün olduğunda kayıtlara geçirilir ve sonraki bağımsız değişkenler yığına geçirilir.

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

Şuna eşdeğerdir:

```cpp
void __stdcall CMyClass::mymethod() { return; }
```

## <a name="example"></a>Örnek

Aşağıdaki örnekte, kullanım **__stdcall** tüm sonuçları `WINAPI` işlevi standart arama olarak işlenen türleri:

```cpp
// Example of the __stdcall keyword
#define WINAPI __stdcall
// Example of the __stdcall keyword on function pointer
typedef BOOL (__stdcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);
```

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
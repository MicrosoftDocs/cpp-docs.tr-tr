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
ms.openlocfilehash: 3abd1d020e4181a42a7bc38319e5e17e69ef0507
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178550"
---
# <a name="__stdcall"></a>__stdcall

**__Stdcall** çağırma kuralı, Win32 API işlevleri çağırmak için kullanılır. Çağıran, yığın temizler, bu nedenle derleyici `vararg` işlevleri **__cdecl**hale getirir. Bu çağırma kuralını kullanan işlevler, bir işlev prototipi gerektirir. **__Stdcall** değiştiricisi Microsoft 'a özgüdür.

## <a name="syntax"></a>Sözdizimi

> *dönüş türü* **\_\_stdcall** *işlevi-adı*[ **(** *bağımsız değişken-listesi* **)** ]

## <a name="remarks"></a>Açıklamalar

Aşağıdaki liste bu çağırma kuralının uygulamasını gösterir.

|Öğe|Uygulama|
|-------------|--------------------|
|Bağımsız değişken geçirme sırası|Sağdan sola.|
|Bağımsız değişken geçirme kuralı|Bir işaretçi veya başvuru türü geçirilmemişse değere göre.|
|Yığın bakımı sorumluluğu|Çağrılan işlev, kendi bağımsız değişkenlerini yığından çıkarır.|
|Ad düzenleme kuralı|Adın önüne bir alt çizgi (_) eklenir. Adından sonra gelen işareti (@) ve ardından bağımsız değişken listesindeki bayt sayısı (ondalık olarak) gelir. Bu nedenle, `int func( int a, double b )` olarak belirtilen işlev şu şekilde tasarlanmıştır: `_func@12`|
|Durum çevirisi kuralları|Hiçbiri|

[/Gz](../build/reference/gd-gr-gv-gz-calling-convention.md) derleyici seçeneği, farklı bir çağırma kuralıyla açıkça bildirilmeyen tüm işlevler için **__stdcall** belirtir.

Önceki sürümlerle uyumluluk için, [/za \(dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtildiğinde, **_stdcall** **__stdcall** için bir eş anlamlı.

**__Stdcall** değiştirici kullanılarak belirtilen işlevler, [__cdecl](../cpp/cdecl.md)kullanılarak belirtilen işlevlerle aynı şekilde değer döndürür.

ARM ve x64 işlemcilerde **__stdcall** , derleyici tarafından kabul edilir ve yok sayılır; ARM ve x64 mimarilerinde, kurala göre, bağımsız değişkenler mümkün olduğunda kayıtlara geçirilir ve sonraki bağımsız değişkenler yığına geçirilir.

Statik olmayan sınıf işlevleri için, işlev satır dışı olarak tanımlandıysa çağırma kuralı değiştiricinin satır dışı tanımda belirtilmesi gerekmez. Diğer bir deyişle, statik olmayan üye sınıfı yöntemler için tanım noktasında bildirim sırasında belirtilen çağırma kuralı kabul edilir. Bu sınıf tanımı verildiğinde,

```cpp
struct CMyClass {
   void __stdcall mymethod();
};
```

bu

```cpp
void CMyClass::mymethod() { return; }
```

Buna eşdeğerdir

```cpp
void __stdcall CMyClass::mymethod() { return; }
```

## <a name="example"></a>Örnek

Aşağıdaki örnekte, tüm `WINAPI` işlev türlerinde standart çağrı olarak işlenen **__stdcall** sonuçlarının kullanılması gerekir:

```cpp
// Example of the __stdcall keyword
#define WINAPI __stdcall
// Example of the __stdcall keyword on function pointer
typedef BOOL (__stdcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);
```

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)

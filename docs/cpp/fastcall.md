---
title: __fastcall
ms.date: 12/17/2018
f1_keywords:
- __fastcall_cpp
- __fastcall
- _fastcall
helpviewer_keywords:
- __fastcall keyword [C++]
ms.assetid: bb5b9c8a-dfad-450c-9119-0ac2bc59544f
ms.openlocfilehash: d4b650542a3a85c8f0008374abef02686c5491a3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188928"
---
# <a name="__fastcall"></a>__fastcall

**Microsoft 'a özgü**

**__Fastcall** çağırma kuralı, işlevlerdeki bağımsız değişkenlerin, mümkün olduğunda yazmaçlara geçirileceğini belirtir. Bu çağırma kuralı yalnızca x86 mimarisi için geçerlidir. Aşağıdaki liste bu çağırma kuralının uygulamasını gösterir.

|Öğe|Uygulama|
|-------------|--------------------|
|Bağımsız değişken geçirme sırası|Bağımsız değişken listesinde soldan sağa bulunan ilk iki DWORD veya daha küçük bağımsız değişken ECX ve EDX yazmaçlarında geçirilir; Tüm diğer bağımsız değişkenler yığına sağdan sola geçirilir.|
|Yığın bakımı sorumluluğu|Çağrılan işlev, yığındaki bağımsız değişkenleri pop 'ları.|
|Ad düzenleme kuralı|Oturum açma (\@), adlara ön ek olarak eklenir; bir at işareti ve ardından parametre listesindeki bayt sayısı (ondalık), adlara son olarak sabitlenmiştir.|
|Durum çevirisi kuralları|Durum çevirisi yapılmaz.|

> [!NOTE]
> Gelecekteki derleyici sürümleri, parametreleri depolamak için farklı Yazmaçları kullanabilir.

[/Gr](../build/reference/gd-gr-gv-gz-calling-convention.md) derleyici seçeneğinin kullanılması, işlev çakışan bir öznitelik kullanılarak bildirilemediği veya işlevin adı `main`olmadığı sürece modüldeki her işlevin **__fastcall** olarak derlenmesine neden olur.

**__Fastcall** anahtar sözcüğü, ARM ve x64 mimarileri hedefleyen derleyiciler tarafından kabul edilir ve yok sayılır; bir x64 yongasında, kurala göre ilk dört bağımsız değişken mümkün olduğunda yazmaçlara geçirilir ve yığında ek bağımsız değişkenler geçirilir. Daha fazla bilgi için bkz. [x64 çağırma kuralı](../build/x64-calling-convention.md). ARM yongasında, en fazla dört tamsayı bağımsız değişkeni ve sekiz kayan nokta bağımsız değişkeni, yazmaçlara geçirilebilir ve ek bağımsız değişkenler yığına geçirilir.

Statik olmayan sınıf işlevleri için, işlev satır dışı olarak tanımlandıysa çağırma kuralı değiştiricinin satır dışı tanımda belirtilmesi gerekmez. Diğer bir deyişle, statik olmayan üye sınıfı yöntemler için tanım noktasında bildirim sırasında belirtilen çağırma kuralı kabul edilir. Bu sınıf tanımını ele alalım:

```cpp
struct CMyClass {
   void __fastcall mymethod();
};
```

bu:

```cpp
void CMyClass::mymethod() { return; }
```

şuna eşdeğerdir:

```cpp
void __fastcall CMyClass::mymethod() { return; }
```

Önceki sürümlerle uyumluluk için, [/za \(dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtildiğinde, **_fastcall** **__fastcall** için bir eş anlamlı.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, `DeleteAggrWrapper` işlev, Yazmaçlarda bağımsız değişkenleri geçti:

```cpp
// Example of the __fastcall keyword
#define FASTCALL    __fastcall

void FASTCALL DeleteAggrWrapper(void* pWrapper);
// Example of the __ fastcall keyword on function pointer
typedef BOOL (__fastcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)

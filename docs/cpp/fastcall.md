---
description: 'Hakkında daha fazla bilgi edinin: __fastcall'
title: __fastcall
ms.date: 12/17/2018
f1_keywords:
- __fastcall_cpp
- __fastcall
- _fastcall
helpviewer_keywords:
- __fastcall keyword [C++]
ms.assetid: bb5b9c8a-dfad-450c-9119-0ac2bc59544f
ms.openlocfilehash: 6f4c4f533f0d2337323d486cc9c433898a19e6a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242613"
---
# <a name="__fastcall"></a>__fastcall

**Microsoft'a Özgü**

**`__fastcall`** Çağırma kuralı, işlevler için bağımsız değişkenlerin, mümkün olduğunda yazmaçlara geçirileceğini belirtir. Bu çağırma kuralı yalnızca x86 mimarisi için geçerlidir. Aşağıdaki liste bu çağırma kuralının uygulamasını gösterir.

|Öğe|Uygulama|
|-------------|--------------------|
|Bağımsız değişken geçirme sırası|Bağımsız değişken listesinde soldan sağa bulunan ilk iki DWORD veya daha küçük bağımsız değişken ECX ve EDX yazmaçlarında geçirilir; Tüm diğer bağımsız değişkenler yığına sağdan sola geçirilir.|
|Yığın bakımı sorumluluğu|Çağrılan işlev, yığındaki bağımsız değişkenleri pop 'ları.|
|Ad düzenleme kuralı|At işareti ( \@ ), adlara ön ek olarak, parametre listesindeki bayt sayısı (ondalık olarak), adlara son olarak sabitlenmiştir.|
|Durum çevirisi kuralları|Durum çevirisi yapılmaz.|

> [!NOTE]
> Gelecekteki derleyici sürümleri, parametreleri depolamak için farklı Yazmaçları kullanabilir.

[/Gr](../build/reference/gd-gr-gv-gz-calling-convention.md) derleyici seçeneğinin kullanılması, **`__fastcall`** işlev çakışan bir öznitelik kullanılarak bildirilemediği veya işlevin adı olduğu sürece, modüldeki her işlevin olarak derlenmesine neden olur `main` .

**`__fastcall`** Anahtar sözcüğü, ARM ve x64 mimarileri hedefleyen derleyiciler tarafından kabul edilir ve yok sayılır; bir x64 yongasında, kurala göre, ilk dört bağımsız değişken mümkün olduğunda yazmaçlara geçirilir ve yığında ek bağımsız değişkenler geçirilir. Daha fazla bilgi için bkz. [x64 çağırma kuralı](../build/x64-calling-convention.md). ARM yongasında, en fazla dört tamsayı bağımsız değişkeni ve sekiz kayan nokta bağımsız değişkeni, yazmaçlara geçirilebilir ve ek bağımsız değişkenler yığına geçirilir.

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

Önceki sürümlerle uyumluluk için,  **`__fastcall`** [/za \( Disable dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtildiğinde _fastcall için bir eş anlamlı.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, işlev, `DeleteAggrWrapper` Yazmaçlarda bağımsız değişkenleri geçti:

```cpp
// Example of the __fastcall keyword
#define FASTCALL    __fastcall

void FASTCALL DeleteAggrWrapper(void* pWrapper);
// Example of the __ fastcall keyword on function pointer
typedef BOOL (__fastcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız değişken geçirme ve adlandırma kuralları](../cpp/argument-passing-and-naming-conventions.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)

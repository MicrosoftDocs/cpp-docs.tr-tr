---
title: __cdecl
ms.date: 10/09/2018
f1_keywords:
- __cdecl_cpp
- __cdecl
- _cdecl
- cdecl
helpviewer_keywords:
- __cdecl keyword [C++]
ms.assetid: 1ff1d03e-fb4e-4562-8be1-74f1ad6427f1
ms.openlocfilehash: f4cca797c0bff94a54b0f3302c6c475908870a99
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857625"
---
# <a name="__cdecl"></a>__cdecl

**__cdecl** , C ve C++ programları için varsayılan çağırma kuralıdır. Yığın, arayan tarafından temizlendiği için `vararg` işlevleri gerçekleştirebilir. **__Cdecl** çağırma kuralı, yığın Temizleme kodunu dahil etmek için her bir işlev çağrısını gerektirdiğinden [__stdcall](../cpp/stdcall.md)daha büyük yürütülebilir dosyalar oluşturur. Aşağıdaki liste bu çağırma kuralının uygulamasını gösterir. **__Cdecl** değiştiricisi Microsoft 'a özgüdür.

|Öğe|Uygulama|
|-------------|--------------------|
|Bağımsız değişken geçirme sırası|Sağdan sola.|
|Yığın bakımı sorumluluğu|Çağıran işlev, yığından bağımsız değişkenleri açar.|
|Ad düzenleme kuralı|C bağlantısı kullanan \__cdecl işlevlerinin verildiği durumlar dışında alt çizgi karakteri (_) adlara önek olarak eklenir.|
|Durum çevirisi kuralları|Durum çevirisi yapılmaz.|

> [!NOTE]
>  İlgili bilgiler için bkz. [düzenlenmiş adlar](../build/reference/decorated-names.md).

**__Cdecl** değiştiricisini bir değişken veya işlev adından önce koyun. C adlandırma ve çağırma kuralları varsayılan olduğu için, x86 kodundaki **__cdecl** kullanmanız gereken tek zaman, `/Gv` (vectorcall), `/Gz` (stdcall) veya `/Gr` (fastcall) derleyici seçeneğini belirtişinizde olur. [/GD](../build/reference/gd-gr-gv-gz-calling-convention.md) derleyici seçeneği **__cdecl** çağırma kuralını zorlar.

ARM ve x64 işlemcilerde **__cdecl** kabul edilir ancak genellikle derleyici tarafından yok sayılır. ARM ve x64 kuralına göre, bağımsız değişkenler mümkün olduğunda kayıtlarda geçirilir ve sonraki bağımsız değişkenler yığında geçirilir. X64 kodunda, **/GV** derleyici seçeneğini geçersiz kılmak için **__cdecl** kullanın ve varsayılan x64 çağırma kuralını kullanın.

Statik olmayan sınıf işlevleri için, işlev satır dışı olarak tanımlandıysa çağırma kuralı değiştiricinin satır dışı tanımda belirtilmesi gerekmez. Diğer bir deyişle, statik olmayan üye sınıfı yöntemler için tanım noktasında bildirim sırasında belirtilen çağırma kuralı kabul edilir. Bu sınıf tanımını ele alalım:

```cpp
struct CMyClass {
   void __cdecl mymethod();
};
```

bu:

```cpp
void CMyClass::mymethod() { return; }
```

şuna eşdeğerdir:

```cpp
void __cdecl CMyClass::mymethod() { return; }
```

Önceki sürümlerle uyumluluk için **cdecl** ve **_cdecl** , [/za \(dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtilmediği takdirde **__cdecl** için bir eş anladır.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, derleyicinin C adlandırmasını kullanması ve `system` işlevi için çağrı kurallarını kullanması talimat verilmiştir.

```cpp
// Example of the __cdecl keyword on function
int __cdecl system(const char *);
// Example of the __cdecl keyword on function pointer
typedef BOOL (__cdecl *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);
```

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
---
description: 'Hakkında daha fazla bilgi edinin: __cdecl'
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
ms.openlocfilehash: de6d34aa70353f65191c0c36c790d517a1fbbf0e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308581"
---
# <a name="__cdecl"></a>__cdecl

**`__cdecl`** , C ve C++ programları için varsayılan çağırma kuralıdır. Yığın, arayan tarafından temizlendiği için `vararg` işlevleri gerçekleştirebilir. **`__cdecl`** Çağırma kuralı, yığın Temizleme kodunu dahil etmek için her bir işlev çağrısını gerektirdiğinden [__stdcall](../cpp/stdcall.md)daha büyük yürütülebilir dosyalar oluşturur. Aşağıdaki liste bu çağırma kuralının uygulamasını gösterir. **`__cdecl`** Değiştirici, Microsoft 'a özgüdür.

|Öğe|Uygulama|
|-------------|--------------------|
|Bağımsız değişken geçirme sırası|Sağdan sola.|
|Yığın bakımı sorumluluğu|Çağıran işlev, yığından bağımsız değişkenleri açar.|
|Ad düzenleme kuralı|\_C bağlantısı kullanan _cdecl işlevleri aktarıldığında, alt çizgi karakteri (_) adların önüne eklenir.|
|Durum çevirisi kuralları|Durum çevirisi yapılmaz.|

> [!NOTE]
> İlgili bilgiler için bkz. [düzenlenmiş adlar](../build/reference/decorated-names.md).

**`__cdecl`** Değiştiricisini bir değişken veya işlev adından önce koyun. C adlandırma ve çağırma kuralları varsayılan olduğu için, x86 kodunda kullanmanız gereken tek zaman **`__cdecl`** `/Gv` (vectorcall), `/Gz` (stdcall) veya `/Gr` (fastcall) derleyici seçeneğini belirtişinizde olur. [/GD](../build/reference/gd-gr-gv-gz-calling-convention.md) derleyici seçeneği **`__cdecl`** çağırma kuralını zorlar.

ARM ve x64 işlemcilerde, **`__cdecl`** kabul edilir ancak genellikle derleyici tarafından yok sayılır. ARM ve x64 kuralına göre, bağımsız değişkenler mümkün olduğunda kayıtlarda geçirilir ve sonraki bağımsız değişkenler yığında geçirilir. X64 kodunda, **`__cdecl`** **/GV** derleyici seçeneğini geçersiz kılmak için kullanın ve varsayılan x64 çağırma kuralını kullanın.

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

Önceki sürümlerle uyumluluk için, **cdecl** ve **_cdecl** , **`__cdecl`** derleyici seçeneği [/za \( Disable dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) ' ın bir eşanlamlısıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, derleyicinin işlev için C adlandırma ve çağırma kuralları kullanması talimatı vardır `system` .

```cpp
// Example of the __cdecl keyword on function
int __cdecl system(const char *);
// Example of the __cdecl keyword on function pointer
typedef BOOL (__cdecl *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);
```

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız değişken geçirme ve adlandırma kuralları](../cpp/argument-passing-and-naming-conventions.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)

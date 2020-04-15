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
ms.openlocfilehash: b4a86c49880b0c40d402c7cec863f79e24bc4dc1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371562"
---
# <a name="__cdecl"></a>__cdecl

**__cdecl** C ve C++ programları için varsayılan çağrı kuralıdır. Yığın arayan tarafından temizlenerek, işlevleri yapabilir. `vararg` __cdecl **__cdecl** çağrı [kuralı,](../cpp/stdcall.md)her işlev çağrısının yığın temizleme kodunu içermesini gerektirdiğinden, __stdcall daha büyük yürütülebilir ler oluşturur. Aşağıdaki liste bu çağırma kuralının uygulamasını gösterir. **__cdecl** değiştirici Microsoft'a özgüdür.

|Öğe|Uygulama|
|-------------|--------------------|
|Bağımsız değişken geçirme sırası|Sağdan sola.|
|Yığın bakımı sorumluluğu|Çağıran işlev, yığından bağımsız değişkenleri açar.|
|Ad düzenleme kuralı|C bağlantısını kullanan \__cdecl işlevlerin dışa aktarılması dışında alt karakter (_) adlara önceden yapıştırılır.|
|Durum çevirisi kuralları|Durum çevirisi yapılmaz.|

> [!NOTE]
> İlgili bilgiler için [Bkz. Dekore Edilmiş Adlar.](../build/reference/decorated-names.md)

**__cdecl** değiştiriciyi bir değişken veya işlev adından önce yerleştirin. C adlandırma ve çağırma kuralları varsayılan olduğundan, x86 kodunda **__cdecl** kullanmanız gereken tek `/Gv` zaman (vectorcall), `/Gz` (stdcall) veya `/Gr` (fastcall) derleyici seçeneğini belirttiğiniz zamandır. [/Gd](../build/reference/gd-gr-gv-gz-calling-convention.md) derleyicisi **seçeneği, çağrı __cdecl** zorlar.

ARM ve x64 işlemcilerde **__cdecl** kabul edilir, ancak genellikle derleyici tarafından göz ardı edilir. ARM ve x64 kuralına göre, bağımsız değişkenler mümkün olduğunda kayıtlarda geçirilir ve sonraki bağımsız değişkenler yığında geçirilir. x64 kodunda, **/Gv** derleyici seçeneğini geçersiz kılmak ve varsayılan x64 çağrı kuralını kullanmak için **__cdecl** kullanın.

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

Önceki sürümlerle uyumluluk için, derleyici seçeneği [/Za \(Dil uzantıları](../build/reference/za-ze-disable-language-extensions.md) belirtilmedikçe, **cdecl** ve **_cdecl** **__cdecl** eşanlamlıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, derleyiciişlev için C adlandırma ve çağrı kuralları `system` kullanmak için talimat verilir.

```cpp
// Example of the __cdecl keyword on function
int __cdecl system(const char *);
// Example of the __cdecl keyword on function pointer
typedef BOOL (__cdecl *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);
```

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)

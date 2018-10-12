---
title: __cdecl | Microsoft Docs
ms.custom: ''
ms.date: 10/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __cdecl_cpp
- __cdecl
- _cdecl
- cdecl
dev_langs:
- C++
helpviewer_keywords:
- __cdecl keyword [C++]
ms.assetid: 1ff1d03e-fb4e-4562-8be1-74f1ad6427f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 085d8a49ed3c66f96bf8c2b8bdae7ca54cf3bef6
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163783"
---
# <a name="cdecl"></a>__cdecl

**Microsoft'a özgü**

**__cdecl** çağırma kuralı C ve C++ programları için varsayılan değerdir. Yığın arayan tarafından temizlendiği için bunu yapabilirsiniz `vararg` işlevleri. **__Cdecl** çağırma kuralı, daha büyük yürütülebilir dosyalar oluşturur [__stdcall](../cpp/stdcall.md), çünkü her işlev çağrısının yığın temizleme kodunu içermesini gerektirir. Aşağıdaki liste bu çağırma kuralının uygulamasını gösterir.

|Öğe|Uygulama|
|-------------|--------------------|
|Bağımsız değişken geçirme sırası|Sağdan sola.|
|Yığın bakımı sorumluluğu|Çağıran işlev, yığından bağımsız değişkenleri açar.|
|Ad düzenleme kuralı|Alt çizgi karakteri (_) önüne eklenmesi dışında olduğunda adlarının \_C bağlantısı kullanan _cdecl işlevleri dışa aktarılır.|
|Durum çevirisi kuralları|Durum çevirisi yapılmaz.|

> [!NOTE]
>  İlgili bilgiler için bkz. [düzenlenmiş adlar](../build/reference/decorated-names.md).

Bir yerde **__cdecl** değiştiricisini bir değişken veya işlev adı. C adlandırma ve çağırma kuralları varsayılan olduğu için yalnızca bir kez kullanmalısınız **__cdecl** belirtmiş olduğunuz durumdur içinde x86 kodudur `/Gv` (vectorcall), `/Gz` (stdcall) veya `/Gr` (fastcall) derleyici seçeneği. [/Gd](../build/reference/gd-gr-gv-gz-calling-convention.md) derleyici seçeneğini zorlar **__cdecl** çağırma kuralı.

ARM ve x64 işlemciler **__cdecl** kabul edilir, ancak genellikle derleyici tarafından yok sayıldı. ARM ve x64 kuralına göre, bağımsız değişkenler mümkün olduğunda kayıtlarda geçirilir ve sonraki bağımsız değişkenler yığında geçirilir. X64 içindeki kod, kullanın **__cdecl** geçersiz kılmak için **GV** derleyici seçeneği ve varsayılan x64 çağırma kuralını kullanın.

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

Önceki sürümlerle uyumluluk için **cdecl** ve **_cdecl** ilişkin bir eşanlam olan **__cdecl** sürece derleyici seçeneği [/Za \(devre dışı bırak Dil uzantılarını)](../build/reference/za-ze-disable-language-extensions.md) belirtilir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, derleyicinin C adlandırma ve için çağrı kurallarını kullanması talimat verilmiştir `system` işlevi.

```cpp
// Example of the __cdecl keyword on function
int __cdecl system(const char *);
// Example of the __cdecl keyword on function pointer
typedef BOOL (__cdecl *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);
```

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
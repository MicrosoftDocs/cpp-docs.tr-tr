---
description: 'Daha fazla bilgi edinin: `/Zc:strictStrings` (dize sabit değer türü dönüştürmeyi devre dışı bırak)'
title: /Zc:strictStrings (Değişmez değer dize türü dönüşümünü devre dışı bırakma)
ms.date: 03/06/2018
f1_keywords:
- /Zc:strictStrings
- strictStrings
helpviewer_keywords:
- /Zc:strictStrings
- -Zc compiler options (C++)
- strictStrings
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: b7eb3f3b-82c1-48a2-8e63-66bad7397b46
ms.openlocfilehash: 38c0ac2fe69acd81762fbf26797eece659ee63a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269061"
---
# <a name="zcstrictstrings-disable-string-literal-type-conversion"></a>`/Zc:strictStrings` (Dize sabit değer türü dönüştürmeyi devre dışı bırak)

Belirtildiğinde, derleyici, **`const`** dize sabit değerleri kullanılarak başlatılan işaretçiler için katı nitelik uyumluluğu gerektirir.

## <a name="syntax"></a>Syntax

> **`/Zc:strictStrings`**[**`-`**]

## <a name="remarks"></a>Açıklamalar

**`/Zc:strictStrings`** Belirtilmişse, derleyici, **`const`** bildirime bağlı olarak dize sabit değerleri için ' Array of `const char` ' veya ' Array ' türünde standart C++ niteliklerini uygular `const wchar_t` . Dize sabit değerleri sabittir ve çalışma zamanında bir erişim ihlali hatası ile bir sonucun içeriğini değiştirme girişimi. Dize **`const`** değişmezi kullanarak başlatmak için bir dize işaretçisi bildirmeniz veya **`const_cast`** işaretçi olmayan bir işaretçi başlatmak için açık bir değer kullanmanız gerekir **`const`** . Varsayılan olarak veya **`/Zc:strictStrings-`** belirtilirse, derleyici **`const`** dize sabit değerleri kullanılarak başlatılan dize işaretçileri Için standart C++ niteliklerini zorlamaz.

**`/Zc:strictStrings`** Seçenek varsayılan olarak kapalıdır. [`/permissive-`](permissive-standards-conformance.md)Derleyici seçeneği bu seçeneği örtülü olarak ayarlar, ancak kullanılarak geçersiz kılınabilir **`/Zc:strictStrings-`** .

**`/Zc:strictStrings`** Yanlış kodun derlemesini engellemek için seçeneğini kullanın. Bu örnek, bir basit bildirim hatasının çalışma zamanında kilitlenmeyle nasıl yol gösterdiğini gösterir:

```cpp
// strictStrings_off.cpp
// compile by using: cl /W4 strictStrings_off.cpp
int main() {
   wchar_t* str = L"hello";
   str[2] = L'a'; // run-time error: access violation
}
```

**`/Zc:strictStrings`** Etkinleştirildiğinde, aynı kod bildiriminde bir hata bildirir `str` .

```cpp
// strictStrings_on.cpp
// compile by using: cl /Zc:strictStrings /W4 strictStrings_on.cpp
int main() {
   wchar_t* str = L"hello"; // error: Conversion from string literal
   // loses const qualifier
   str[2] = L'a';
}
```

**`auto`** Bir dize işaretçisi bildirmek için kullanırsanız, derleyici **`const`** sizin için doğru işaretçi türü bildirimini oluşturur. Bir işaretçinin içeriğini değiştirme girişimi **`const`** derleyici tarafından hata olarak bildirilir.

> [!NOTE]
> Visual Studio 2013 içindeki C++ standart kitaplığı, **`/Zc:strictStrings`** hata ayıklama Derlemeleriyle derleyici seçeneğini desteklemez. Yapı çıkışındaki çeşitli [C2665](../../error-messages/compiler-errors-2/compiler-error-c2665.md) hataları görürseniz, bu durum olabilir.

Visual C++ uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini içerecek şekilde değiştirin **`/Zc:strictStrings`** ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[`/Zc` Uyumsuzlu](zc-conformance.md)<br/>

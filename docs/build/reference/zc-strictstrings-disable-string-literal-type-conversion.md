---
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
ms.openlocfilehash: d0fe7a7aa956ebc7662754b039389983d75ff590
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668721"
---
# <a name="zcstrictstrings-disable-string-literal-type-conversion"></a>/Zc:strictStrings (Değişmez değer dize türü dönüşümünü devre dışı bırakma)

Bu seçenek belirtildiğinde, derleyici katı gerektirir `const`-dize değişmez değerleri kullanılarak başlatılan işaretçiler için nitelik uyumu.

## <a name="syntax"></a>Sözdizimi

> **/ ZC: strictstrings**[**-**]

## <a name="remarks"></a>Açıklamalar

Varsa **/ZC: strictstrings** belirtilirse, derleyici standart C++ zorlar `const` niteliklerini dize değişmez değerleri, türü olarak ' dizi `const char`' veya ' dizi `const wchar_t`' bildirimi bağlı olarak. Dize değişmezleri sabittir ve bir tanesinin içeriği değiştirme girişimi çalışma zamanında bir erişim ihlali hatasına neden olur. Bir dize işaretçisi olarak bildirilmelidir `const` dize değişmez değeri kullanarak başlatmak veya açık bir kullanmak için `const_cast` olmayan bir başlatmak için`const` işaretçi. Varsayılan olarak veya **/Zc:strictStrings-** belirtilirse, derleyici standart C++ zorlamaz `const` niteliklerini dize değişmez değerleri kullanılarak başlatılan dize işaretçileri için.

**/ZC: strictstrings** seçeneği varsayılan olarak kapalıdır. [/ Permissive-](permissive-standards-conformance.md) derleyici seçeneği, bu seçenek örtük olarak ayarlar, ancak kullanarak kılınabilir **/Zc:strictStrings-**.

Kullanım **/ZC: strictstrings** yanlış kod derlemesini önlemek için seçeneği. Bu örnek nasıl basit bir bildirim hatasının çalışma zamanında çökmesine neden geliyor gösterir:

```cpp
// strictStrings_off.cpp
// compile by using: cl /W4 strictStrings_off.cpp
int main() {
   wchar_t* str = L"hello";
   str[2] = L'a'; // run-time error: access violation
}
```

Zaman **/ZC: strictstrings** olduğu aynı kodu bildiriminde hata raporları etkin `str`.

```cpp
// strictStrings_on.cpp
// compile by using: cl /Zc:strictStrings /W4 strictStrings_on.cpp
int main() {
   wchar_t* str = L"hello"; // error: Conversion from string literal
   // loses const qualifier
   str[2] = L'a';
}
```

Kullanırsanız `auto` bir dize işaretçisi bildirirseniz, derleyici doğru oluşturur ve `const` işaretçisi türü bildirimini sizin için. İçeriğini değiştirme girişimi bir `const` işaretçi hata olarak derleyici tarafından raporlanır.

> [!NOTE]
> Visual Studio 2013 C++ Standart Kitaplığı desteklemediği **/ZC: strictstrings** debug derleyici seçeneğini oluşturur. Birkaç görürseniz [C2665](../../error-messages/compiler-errors-2/compiler-error-c2665.md) hataları derleme çıkışı, bu neden olabilir.

Visual C++'ta uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/ZC: strictstrings** seçip **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)<br/>

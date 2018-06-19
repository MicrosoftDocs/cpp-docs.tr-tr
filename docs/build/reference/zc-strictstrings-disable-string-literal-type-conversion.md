---
title: '/ ZC: strictstrings (dize değişmez değer türü dönüşümünü devre dışı bırakma) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:strictStrings
- strictStrings
dev_langs:
- C++
helpviewer_keywords:
- /Zc:strictStrings
- -Zc compiler options (C++)
- strictStrings
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: b7eb3f3b-82c1-48a2-8e63-66bad7397b46
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7025a4bae2d4a7474cb366b041a3c62f3d7db819
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379945"
---
# <a name="zcstrictstrings-disable-string-literal-type-conversion"></a>/Zc:strictStrings (Değişmez değer dize türü dönüşümünü devre dışı bırakma)

Belirtildiğinde, derleyici katı gerektirir `const`-dize değişmez değerleri kullanarak tarafından başlatılan işaretçileri niteliğe uygunluk.

## <a name="syntax"></a>Sözdizimi

> **/ ZC: strictstrings**[**-**]

## <a name="remarks"></a>Açıklamalar

Varsa **/ZC: strictstrings** belirtilirse, standart C++ Derleyici zorlar `const` türü olarak dize değişmez değerleri nitelikleri ' dizisi `const char`' veya ' dizisi `const wchar_t`' bildirimi bağlı olarak. Dize değişmez değerleri sabittir ve bir içeriğini değiştirme girişimi çalışma zamanında bir erişim ihlali hata oluşur. Dize işaretçisi olarak bildirilmelidir `const` bir değişmez dize değeri kullanarak başlatmak veya açık bir kullanmak için `const_cast` olmayan bir başlatılamadı`const` işaretçi. Varsayılan olarak, veya **/Zc:strictStrings-** belirtilirse, derleyici, standart C++ zorlamaz `const` nitelikleri dize işaretçileri dize değişmez değerleri kullanarak başlatıldı.

**/ZC: strictstrings** seçeneği varsayılan olarak kapalıdır. [/ İzin veren-](permissive-standards-conformance.md) derleyici seçeneği, bu seçenek örtük olarak ayarlar, ancak kullanarak kılınabilir **/Zc:strictStrings-**.

Kullanım **/ZC: strictstrings** hatalı kod derleme önlemek için seçeneği. Bu örnek nasıl basit bildirimi hata çökmeyle için çalışma zamanında müşteri adayları gösterir:

```cpp
// strictStrings_off.cpp
// compile by using: cl /W4 strictStrings_off.cpp
int main() {
   wchar_t* str = L"hello";
   str[2] = L'a'; // run-time error: access violation
}
```

Zaman **/ZC: strictstrings** olan etkinse, aynı kod bildirimi hata raporları `str`.

```cpp
// strictStrings_on.cpp
// compile by using: cl /Zc:strictStrings /W4 strictStrings_on.cpp
int main() {
   wchar_t* str = L"hello"; // error: Conversion from string literal
   // loses const qualifier
   str[2] = L'a';
}
```

Kullanırsanız `auto` dize işaretçisi bildirmek için derleyici doğru oluşturur `const` , işaretçi türü bildirimi. İçeriğini değiştirme girişimi bir `const` işaretçi hata olarak derleyici tarafından bildirilir.

> [!NOTE]
> C++ Standart Kitaplığı'nda [!INCLUDE[cpp_dev12_long](../../build/reference/includes/cpp_dev12_long_md.md)] desteklemediği **/ZC: strictstrings** debug derleyici seçeneği oluşturur. Birkaç görürseniz [C2665](../../error-messages/compiler-errors-2/compiler-error-c2665.md) , yapı hataları çıkışı, bu neden olabilir.

Visual c++ uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/ZC: strictstrings** ve ardından **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)<br/>

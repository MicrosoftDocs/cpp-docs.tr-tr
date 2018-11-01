---
title: _SCL_SECURE_NO_WARNINGS
ms.date: 11/04/2016
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
helpviewer_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
ms.openlocfilehash: 77c60aed511fc3dbbea2d74e83e36dae735dcb0e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578419"
---
# <a name="sclsecurenowarnings"></a>_SCL_SECURE_NO_WARNINGS

C++ Standart Kitaplığı'nda güvenli olmayan yöntemlerden birini çağırma sonuçlanıyor [Derleyici Uyarısı (Düzey 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Bu uyarıyı devre dışı bırakmak için kodunuzda makrosu _scl_secure_no_warnıngs tanımlayın:

```cpp
#define _SCL_SECURE_NO_WARNINGS
```

Önceden derlenmiş üst bilgiler kullanıyorsanız, herhangi bir C çalışma zamanı kitaplığı veya standart kitaplığı üst bilgiler dahil etmeden önce bu yönerge, önceden derlenmiş üst bilgi dosyanızda yerleştirin. Önceden derlenmiş üstbilgi dosyasını dahil etmeden önce bir bağımsız kaynak kodu dosyasında koyarsanız, derleyici tarafından yoksayılır.

## <a name="remarks"></a>Açıklamalar

Uyarıyı C4996 devre dışı bırakmak için kullanabileceğiniz diğer yöntemler şunlardır:

- Kullanarak [/D (önişlemci tanımları)](../build/reference/d-preprocessor-definitions.md) derleyici seçeneği:

   > cl [derleyici seçenekleri diğer] /D_SCL_SECURE_NO_WARNINGS myfile.cpp

- Kullanarak [/w](../build/reference/compiler-option-warning-level.md) derleyici seçeneği:

   > cl /wd4996 [derleyici seçenekleri diğer] myfile.cpp

- Kullanarak [#pragma Uyarısı](../preprocessor/warning.md) yönergesi:

   ```cpp
   #pragma warning(disable:4996)
   ```

Ayrıca, el ile C4996 bir uyarı ile düzeyini değiştirebilirsiniz **/w\<l >\<n >** derleyici seçeneği. Örneğin, C4996 düzey 4 uyarısı ayarlamak için şunu yazın:

> cl /w44996 [derleyici seçenekleri diğer] myfile.cpp

Daha fazla bilgi için [/w, /W0, / W1, / w2, / W3, / W4, / W1, / w2, / W3, / W4, /Wall, WD, / we Wo, wv, /WX (uyarı düzeyi)](../build/reference/compiler-option-warning-level.md).

## <a name="see-also"></a>Ayrıca bkz.

[Güvenli Kitaplıklar: C++ Standart Kitaplık](../standard-library/safe-libraries-cpp-standard-library.md)<br/>

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
ms.openlocfilehash: d19d47fe7120301740e1431765fc6edbeaa48c60
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448199"
---
# <a name="sclsecurenowarnings"></a>_SCL_SECURE_NO_WARNINGS

C++ Standart kitaplıkta güvensiz olabilecek yöntemlerin herhangi birini çağırmak, [Derleyici Uyarısı (düzey 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Bu uyarıyı devre dışı bırakmak için kodunuzda _SCL_SECURE_NO_UYARıLAR makrosunu tanımlayın:

```cpp
#define _SCL_SECURE_NO_WARNINGS
```

Önceden derlenmiş üstbilgiler kullanıyorsanız, herhangi bir C çalışma zamanı kitaplığı veya standart kitaplık üst bilgisini eklemeden önce bu yönergeyi ön derlenmiş üstbilgi dosyanıza koyun. Ön derlenmiş üstbilgi dosyasını eklemeden önce tek bir kaynak kodu dosyasına yerleştirirseniz, derleyici tarafından yok sayılır.

## <a name="remarks"></a>Açıklamalar

Uyarı C4996 ' yi devre dışı bırakmak için diğer yollar şunlardır:

- [/D (Önişlemci tanımları)](../build/reference/d-preprocessor-definitions.md) derleyici seçeneğini kullanma:

   > CL/D_SCL_SECURE_NO_WARNINGS [diğer derleyici seçenekleri] dosyam. cpp

- [/W](../build/reference/compiler-option-warning-level.md) derleyici seçeneğini kullanma:

   > CL/wd4996 [diğer derleyici seçenekleri] dosyam. cpp

- [#Pragma uyarı](../preprocessor/warning.md) yönergesini kullanma:

   ```cpp
   #pragma warning(disable:4996)
   ```

Ayrıca, C4996 ' in Level **\<l >\<n >** derleyici seçeneği ile uyarı düzeyini el ile değiştirebilirsiniz. Örneğin, Uyarı C4996 ' yi düzey 4 ' e ayarlamak için:

> CL/w44996 [diğer derleyici seçenekleri] dosyam. cpp

Daha fazla bilgi için bkz. [/w,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/duvar,/WD,/we,/Wo,/WV,/WX (uyarı düzeyi)](../build/reference/compiler-option-warning-level.md).

## <a name="see-also"></a>Ayrıca bkz.

[Güvenli Kitaplıklar: C++ Standart Kitaplığı](../standard-library/safe-libraries-cpp-standard-library.md)

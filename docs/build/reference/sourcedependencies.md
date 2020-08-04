---
title: /sourceDependencies (rapor kaynak düzeyi bağımlılıkları)
description: Microsoft C++ ' da/sourceDependencies derleyici seçeneğine başvuru kılavuzu.
ms.date: 07/29/2020
f1_keywords:
- /sourceDependencies
helpviewer_keywords:
- /sourceDependencies compiler option
- /sourceDependencies
ms.openlocfilehash: 3198353ea7569c426a556522d6b931fe23c7f12c
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87528074"
---
# <a name="sourcedependencies-report-source-level-dependencies"></a>`/sourceDependencies`(Rapor kaynak düzeyi bağımlılıkları)

Derleyiciye derleme sırasında kullanılan kaynak düzeyi bağımlılıklarını ayrıntılarıyla gösteren bir JSON dosyası oluşturmasını söyler.

JSON dosyası, aşağıdakiler dahil olmak üzere kaynak bağımlılıklarının bir listesini içerir:
- Üst bilgi dosyaları (geçişli ve doğrudan eklenen üst bilgiler).
- Kullanılan PCH ( **`/Yu`** belirtilmişse).
- İçeri aktarılan modüller ve içeri aktarılan üst bilgi birimleri (geçişli ve doğrudan içeri aktarılan modüller/başlık birimleri).

## <a name="syntax"></a>Syntax

> **`/sourceDependencies`***dosya adı*\
> **`/sourceDependencies`***Dizin*

## <a name="arguments"></a>Arguments

*kısaltın*\
Derleyici, kaynak bağımlılığı çıkışını, göreli veya mutlak bir yol içerebilen belirtilen dosya adına yazar.

*dizinden*\
Bağımsız değişken bir dizin ise, derleyici belirtilen dizinde kaynak bağımlılığı dosyaları oluşturur. Çıkış dosyası adı, girdi dosyasının tam adına, eklenen bir uzantıya göre belirlenir *`.json`* . Örneğin, derleyiciye girilen dosya ise *`main.cpp`* , oluşturulan çıkış dosya adı olur *`main.cpp.json`* .

## <a name="remarks"></a>Açıklamalar

**`/sourceDependencies`** Derleyici seçeneği Visual Studio 2019 sürüm 16,7 ' den başlayarak kullanılabilir. Varsayılan olarak etkinleştirilmemiştir.

**`/MP`** Derleyici seçeneğini belirttiğinizde, **`/sourceDependencies`** bir dizin bağımsız değişkeniyle kullanmanızı öneririz. Tek bir dosya adı bağımsız değişkeni sağlarsanız, derleyicinin iki örneği çıkış dosyasını eşzamanlı olarak açmayı deneyebilir ve hataya neden olabilir. Hakkında daha fazla bilgi için **`/MP`** bkz. [ `/MP` (birden çok işlemle derleme)](mp-build-with-multiple-processes.md).

Önemli olmayan bir derleyici hatası oluştuğunda, bağımlılık bilgileri yine de çıkış dosyasına yazılır.

Tüm dosya yolları çıktıda mutlak yollar olarak görünür.

### <a name="examples"></a>Örnekler

Aşağıdaki örnek kod verildiğinde:

```cpp
// main.cpp
#include "header.h"
import m;
import "other.h";

int main() { }
```

**`/sourceDependencies`** Derleyici seçeneklerinizin geri kalanı ile birlikte kullanabilirsiniz:

> `cl ... /sourceDependencies output.json ... main.cpp`

`...`Diğer derleyici seçeneklerinizi temsil eder. Bu komut satırı *`output.json`* , şu gibi içeriğe sahip BIR JSON dosyası üretir:

```JSON
{
    "Version": "1.0",
    "Data": {
        "Source": "C:\\...\\main.cpp",
        "PCH": "C:\\...\\pch.pch",
        "Includes": [
            "C:\\...\\header.h"
        ],
        "Modules": [
            "C:\\...\\m.ifc",
            "C:\\...\\other.h.ifc"
        ]
    }
}
```

`...`Raporlanan yolları kısaltılabilir. rapor, mutlak yolları içerir. Bildirilen yollar derleyicinin bağımlılıkları bulduğu yere bağlıdır. Sonuçlar beklenmiyorsa, projenizin içerme yolu ayarlarını denetlemek isteyebilirsiniz.

### <a name="to-set-the-sourcedependencies-compiler-option-in-visual-studio"></a>Visual Studio 'da/sourceDependencies derleyici seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** kutusunda, *`/sourceDependencies: <filename>`* değişikliklerinizi kaydetmek için **Tamam** ' ı ve ardından **Uygula** ' yı seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bu seçeneğin programlı bir eşdeğeri yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyicisi seçenekleri](compiler-options.md)<br/>
[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)<br/>

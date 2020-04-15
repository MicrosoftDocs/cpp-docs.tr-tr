---
title: MSVC Derleyicisi Komut Satırı Söz Dizimi
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
ms.openlocfilehash: 6a56474b537d78a3d0bea8a74d9082007cd2e295
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320542"
---
# <a name="compiler-command-line-syntax"></a>Derleyici Komut Satırı Sözdizimi

CL komut satırı aşağıdaki sözdizimini kullanır:

```
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]
```

Aşağıdaki tabloda CL komutuna giriş açıklanmaktadır.

|Girdi|Anlamı|
|-----------|-------------|
|*Seçeneği*|Bir veya daha fazla [CL seçeneği.](compiler-options.md) Tüm seçeneklerin tüm belirtilen kaynak dosyalariçin geçerli olduğunu unutmayın. Seçenekler, ileri eğik çizgi (/) veya tire (-) tarafından belirtilir. Bir seçenek bir bağımsız değişken alırsa, seçeneğin açıklaması seçenek ve bağımsız değişkenler arasında bir alana izin verilip verilmediğini belgeler. Seçenek adları (/HELP seçeneği hariç) büyük/küçük harf duyarlıdır. Daha fazla bilgi için [CL Seçenekleri Sırası'na](order-of-cl-options.md) bakın.|
|`file`|Bir veya daha fazla kaynak dosyanın, .obj dosyasının veya kitaplıkların adı. CL kaynak dosyaları derler ve .obj dosyalarının ve kitaplıklarının adlarını bağlayıcıya geçirir. Daha fazla bilgi için [CL Dosya Adı Sözdizimine](cl-filename-syntax.md) bakın.|
|*Lib*|Bir veya daha fazla kitaplık adı. CL bu adları bağlayıcıya geçirir.|
|*komut dosyası*|Birden çok seçenek ve dosya adı içeren bir dosya. Daha fazla bilgi için [CL Komut Dosyaları'na](cl-command-files.md) bakın.|
|*bağlantı-opt*|Bir veya daha fazla [MSVC Bağlantı Seçeneği.](linker-options.md) CL bu seçenekleri bağlayıcıya geçirir.|

Komut satırındaki karakter sayısı işletim sistemi tarafından dikte edilen sınır olan 1024'ü geçmediği sürece, istediğiniz sayıda seçenek, dosya adı ve kitaplık adı belirtebilirsiniz.

cl.exe'nin geri dönüş değeri hakkında bilgi için [cl.exe'nin İade Değeri'ne](return-value-of-cl-exe.md) bakın.

> [!NOTE]
> 1024 karakterin komut satırı giriş sınırının, Windows'un gelecekteki sürümlerinde aynı kalacağı garanti edilmez.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)

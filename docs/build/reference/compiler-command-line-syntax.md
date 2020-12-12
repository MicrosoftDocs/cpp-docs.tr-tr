---
description: 'Daha fazla bilgi edinin: derleyici Command-Line sözdizimi'
title: MSVC derleyici Command-Line sözdizimi
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
ms.openlocfilehash: 91340aa543f0e79d3071b93921742b8147918b2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182222"
---
# <a name="compiler-command-line-syntax"></a>Derleyici Komut Satırı Sözdizimi

CL komut satırı aşağıdaki sözdizimini kullanır:

```
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]
```

Aşağıdaki tabloda CL komutuna giriş açıklanmaktadır.

|Giriş|Anlamı|
|-----------|-------------|
|*seçeneği*|Bir veya daha fazla [CL seçeneği](compiler-options.md). Tüm seçeneklerin belirtilen tüm kaynak dosyalarına uygulanacağını unutmayın. Seçenekler bir eğik çizgi (/) veya tire (-) ile belirtilir. Bir seçenek bir bağımsız değişken alırsa, seçeneğin açıklaması, seçenek ve bağımsız değişkenler arasında bir boşluk olup olmadığını belgeler. Seçenek adları (/HELP seçeneği dışında) büyük/küçük harfe duyarlıdır. Daha fazla bilgi için bkz. [cl seçenekleri sırası](order-of-cl-options.md) .|
|`file`|Bir veya daha fazla kaynak dosyası,. obj dosyası ya da kitaplıkların adı. Kaynak dosyalarını CL ve. obj dosya ve kitaplıklarının adlarını bağlayıcıya geçirir. Daha fazla bilgi için bkz. [CL dosya adı sözdizimi](cl-filename-syntax.md) .|
|*LIB*|Bir veya daha fazla kitaplık adı. CL bu adları bağlayıcıya geçirir.|
|*komut dosyası*|Birden çok seçenek ve dosya adı içeren bir dosya. Daha fazla bilgi için bkz. [CL komut dosyaları](cl-command-files.md) .|
|*bağlantı-opt*|Bir veya daha fazla [MSVC bağlayıcı seçeneği](linker-options.md). CL bu seçenekleri bağlayıcıya geçirir.|

Komut satırındaki karakter sayısı, işletim sistemi tarafından dikte edilen sınırı 1024 ' ı aşmadığı sürece istediğiniz sayıda seçenek, dosya adı ve Kitaplık adı belirtebilirsiniz.

cl.exe dönüş değeri hakkında daha fazla bilgi için bkz. [cl.exedönüş değeri ](return-value-of-cl-exe.md) .

> [!NOTE]
> 1024 karakterlik komut satırı giriş sınırının gelecekteki Windows sürümlerinde aynı kalması garanti edilmez.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)

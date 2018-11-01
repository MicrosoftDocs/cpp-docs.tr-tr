---
title: Derleyici Komut Satırı Sözdizimi
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
ms.openlocfilehash: a350a2cb793630b90143b7d190ada9469a79bfc1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581304"
---
# <a name="compiler-command-line-syntax"></a>Derleyici Komut Satırı Sözdizimi

CL komut satırında aşağıdaki sözdizimini kullanır:

```
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]
```

CL komut girişine aşağıdaki tabloda açıklanmaktadır.

|Giriş|Açıklama|
|-----------|-------------|
|*Seçeneği*|Bir veya daha fazla [CL seçenekleri](../../build/reference/compiler-options.md). Tüm seçenekleri tüm belirtilen kaynak dosyaları için geçerli olduğunu unutmayın. Eğik çizgi (/) veya tire (-) tarafından belirtilen seçenekler. Seçenek ve bağımsız değişkenler boşluk izin verilip verilmediğini seçeneği bir bağımsız değişken, seçeneğin açıklama belgeleri sürerse. (Hariç, / Help seçeneği) seçeneği adları büyük/küçük harfe duyarlıdır. Bkz: [CL seçenekleri sırası](../../build/reference/order-of-cl-options.md) daha fazla bilgi için.|
|`file`|Bir veya daha fazla kaynak dosyaları, .obj dosyaları veya kitaplığı adı. CL kaynak dosyaları derler ve .obj dosyaları ve kitaplıkları adlarını bağlayıcıya iletir. Bkz: [CL dosya adı sözdizimi](../../build/reference/cl-filename-syntax.md) daha fazla bilgi için.|
|*lib*|Bir veya daha fazla kitaplık adları. CL bu adlar bağlayıcıya iletir.|
|*komut dosyası*|Birden fazla seçeneği ve dosya adı içeren bir dosya. Bkz: [CL komut dosyaları](../../build/reference/cl-command-files.md) daha fazla bilgi için.|
|*bağlantı-opt*|Bir veya daha fazla [bağlayıcı seçenekleri](../../build/reference/linker-options.md). Bu seçenekler, CL bağlayıcıya iletir.|

Komut satırında karakter sayısı 1024, işletim sistemi tarafından dikte sınırı aşmadığından sürece herhangi bir sayıda seçenekleri, dosya adları ve kitaplık adlarını belirtebilirsiniz.

Cl.exe dönüş değeri hakkında daha fazla bilgi için bkz. [cl.exe dönüş değeri](../../build/reference/return-value-of-cl-exe.md) .

> [!NOTE]
>  Komut satırı giriş sınırını 1024 karakter gelecekteki Windows sürümlerinde aynı kalması garanti edilmez.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)
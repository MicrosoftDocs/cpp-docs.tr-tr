---
title: Bağlayıcı araçları uyarısı LNK4049 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4049
dev_langs:
- C++
helpviewer_keywords:
- LNK4049
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ad4e4adb492789639c71a25a2db774a80cd77c9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021765"
---
# <a name="linker-tools-warning-lnk4049"></a>Bağlayıcı Araçları Uyarısı LNK4049

Sembol 'symbol' içeri aktarılan yerel olarak tanımlanan

Simgenin hem öğesinden dışarı aktarılan ve programa içeri aktarıldı.

Bu uyarı bağlayıcı tarafından oluşturulan kullanarak bir sembol bildirdiğinizde `__declspec(dllexport)` depolama sınıfı özniteliğini bir nesne dosyasında ve kullanarak referans `__declspec(dllimport)` başka bir öznitelik.

Uyarısı LNK4049 daha genel bir sürümü olan [Bağlayıcı araçları uyarısı LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md). Hangi işlevden alınan sembol başvuruldu belirleyemediğinde bağlayıcı uyarısı LNK4049 oluşturur.

LNK4049 LNK4217 yerine oluşturulduğu yaygın durumlar şunlardır:

- Artımlı bağlamayı kullanarak gerçekleştirme [/INCREMENTAL](../../build/reference/incremental-link-incrementally.md) seçeneği.

- Bütün program iyileştirmesi gerçekleştirme [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) seçeneği.

LNK4049 çözmek için aşağıdakilerden birini deneyin:

- Kaldırma `__declspec(dllimport)` LNK4049 tetikleyen simgenin İleri dönük bildirimi bildirimden olarak adlandırın. İkili bir görüntü içindeki semboller kullanarak arayabilirsiniz **DUMPBIN** yardımcı programı. **DUMPBIN/SEMBOLLER** anahtarı görüntüsü COFF sembol tablosu görüntüler. Daha fazla bilgi için **DUMPBIN** yardımcı programını bkz [DUMPBIN başvurusu](../../build/reference/dumpbin-reference.md).

- Artımlı bağlamayı ve bütün program iyileştirmesi geçici olarak devre dışı bırakın. Uygulama yeniden derlendiğinde, içeri aktarılan sembol başvurulan işlevinin adını içeren uyarısı LNK4217 oluşturur. Kaldırma `__declspec(dllimport)` bildirimden alınan sembol ve artımlı bağlamayı etkinleştir veya bütün program iyileştirmesi gerektiğinde.

Son oluşturulan kodun doğru şekilde davranmaz olsa da, içeri aktarılan işlevi çağırmak için oluşturulan kodu işlevi doğrudan çağırma daha verimli değildir. Seçeneğini kullanarak derleme yaptığınızda bu uyarıyı görünmez [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).

Hakkında daha fazla bilgi almak ve veri bildirimlerini dışarı aktarmak için bkz. [dllexport, dllimport](../../cpp/dllexport-dllimport.md).

## <a name="example"></a>Örnek

Aşağıdaki iki modül bağlama LNK4049 oluşturur. Tek bir dışa aktarılan işlevi içeren bir nesne dosyası birinci modülü oluşturur.

```
// LNK4049a.cpp
// compile with: /c

__declspec(dllexport) int func()
{
   return 3;
}
```

## <a name="example"></a>Örnek

İkinci modül içinde bu işlevi çağrısı yanı sıra ilk modülünde dışarı aktarılan işleve bir ileri dönük bildirimi içeren bir nesne dosyası oluşturur `main` işlevi. Bu modül ilk modülü ile bağlama LNK4049 oluşturur. Kaldırma `__declspec(dllimport)` bildirimi, uyarı giderir.

```
// LNK4049b.cpp
// compile with: /link /WX /LTCG LNK4049a.obj
// LNK4049 expected

__declspec(dllimport) int func();
// try the following line instead
// int func();

int main()
{
   return func();
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Araçları Uyarısı LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md)<br/>
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)
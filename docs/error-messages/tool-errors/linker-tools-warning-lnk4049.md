---
title: Bağlayıcı Araçları Uyarısı LNK4049
ms.date: 04/09/2019
f1_keywords:
- LNK4049
helpviewer_keywords:
- LNK4049
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
ms.openlocfilehash: 357bf5a981dddadfd79d2d6981ccc9c478909097
ms.sourcegitcommit: 0ad3f4517e64900a2702dd3d366586f9e2bce2c2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2019
ms.locfileid: "59477359"
---
# <a name="linker-tools-warning-lnk4049"></a>Bağlayıcı Araçları Uyarısı LNK4049

> Sembol '*sembol*'içinde tanımlanan'*filename.obj*' alınır

Simgenin hem öğesinden dışarı aktarılan ve programa içeri aktarıldı.

Bir nesne dosyasında simge tanımlamak ve kullanarak başvuru olduğunda bu uyarı bağlayıcı tarafından oluşturulan `__declspec(dllimport)` başka bir bildirim değiştirici.

Uyarısı LNK4049 daha genel bir sürümü olan [Bağlayıcı araçları uyarısı LNK4217](linker-tools-warning-lnk4217.md). Sembolü içeri aktarılan bir işlevin veya nesnenin hangi dosya başvurulan belirleyemediğinde uyarısı LNK4049 bağlayıcı oluşturur.

LNK4049 LNK4217 yerine oluşturulduğu yaygın durumlar şunlardır:

- Kullanırken [/INCREMENTAL](../../build/reference/incremental-link-incrementally.md) seçeneği.

- Kullanırken [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) seçeneği.

LNK4049 çözmek için aşağıdaki yordamlardan birini deneyin:

- Kaldırma `__declspec(dllimport)` LNK4049 tetikleyen simgenin İleri dönük bildirimi gelen değiştiricisi. İkili bir görüntü içindeki semboller kullanarak arayabilirsiniz **DUMPBIN** yardımcı programı. **DUMPBIN /SYMBOLS** anahtarı görüntüsü COFF sembol tablosu görüntüler. Daha fazla bilgi için **DUMPBIN** yardımcı programını bkz [DUMPBIN başvurusu](../../build/reference/dumpbin-reference.md).

- Artımlı bağlamayı ve bütün program iyileştirmesi geçici olarak devre dışı bırakın. Yeniden derlenen uygulamanın içeri aktarılan sembol başvuran işlevinin adını içeren uyarısı LNK4217 oluşturur. Kaldırma `__declspec(dllimport)` içeri aktarılan sembol ve artımlı bağlamayı etkinleştir yeniden veya bütün program iyileştirmesi gerektiğinde bildirim değiştirici.

Son oluşturulan kodun doğru şekilde davranır ancak, içeri aktarılan işlevi çağırmak için oluşturulan kodu işlevi doğrudan çağırma değerinden daha az verimlidir. Bu uyarı kullanarak derleme yaptığınızda görünmez [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) seçeneği.

Hakkında daha fazla bilgi almak ve veri bildirimlerini dışarı aktarmak için bkz. [dllexport, dllimport](../../cpp/dllexport-dllimport.md).

## <a name="example"></a>Örnek

Aşağıdaki iki modül bağlama LNK4049 oluşturur. Tek bir dışa aktarılan işlevi içeren bir nesne dosyası birinci modülü oluşturur.

```cpp
// LNK4049a.cpp
// compile with: /c

__declspec(dllexport) int func()
{
   return 3;
}
```

İkinci modül içinde bu işlevi çağrısı yanı sıra ilk modülünde dışarı aktarılan işleve bir ileri dönük bildirimi içeren bir nesne dosyası oluşturur `main` işlevi. Bu modül ilk modülü ile bağlama LNK4049 oluşturur. Kaldırma `__declspec(dllimport)` uyarıyı çözmek için bildirim alanından değiştiricisi.

```cpp
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

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı araçları uyarısı LNK4217](linker-tools-warning-lnk4217.md) \
[Bağlayıcı araçları uyarısı LNK4286](linker-tools-warning-lnk4286.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)
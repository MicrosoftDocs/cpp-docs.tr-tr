---
title: Bağlayıcı Araçları Uyarısı LNK4049
ms.date: 04/15/2019
f1_keywords:
- LNK4049
helpviewer_keywords:
- LNK4049
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
ms.openlocfilehash: a8e4416eafd47f584de4ab1c83aa7303cab0440a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194141"
---
# <a name="linker-tools-warning-lnk4049"></a>Bağlayıcı Araçları Uyarısı LNK4049

> '*filename. obj*' içinde tanımlanan '*symbol*' sembolü içeri aktarıldı

sembol aynı görüntüde dosya *adı. obj* nesne dosyasında tanımlı olsa da *sembol* için [__declspec (dllimport)](../../cpp/dllexport-dllimport.md) belirtildi. Bu uyarıyı çözmek için `__declspec(dllimport)` değiştiricisini kaldırın.

## <a name="remarks"></a>Açıklamalar

Bu uyarı, bir nesne dosyasında bir sembol tanımladığınızda ve başka bir `__declspec(dllimport)` bildirimi değiştiricisini kullanarak ona başvuru yaptığınızda bağlayıcı tarafından oluşturulur.

Uyarı LNK4049, [bağlayıcı araçlarının uyarı LNK4217](linker-tools-warning-lnk4217.md)'in daha genel bir sürümüdür. Bağlayıcı, içeri aktarılan simgeye hangi işlevin veya nesne dosyasının başvurduğunu belirleyememesi durumunda uyarı LNK4049 oluşturur.

LNK4217 yerine LNK4049 'in oluşturulduğu yaygın durumlar şunlardır:

- [/Artımlı](../../build/reference/incremental-link-incrementally.md) seçeneği kullanılırken.

- [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) seçeneği kullanılırken.

LNK4049 çözümlemek için aşağıdaki yordamlardan birini deneyin:

- `__declspec(dllimport)` değiştiricisini, LNK4049 tetiklenen simgenin iletme bildiriminden kaldırın. Bir ikili görüntüde sembolleri, **dumpbin** yardımcı programını kullanarak arayabilirsiniz. **Dumpbin/SYMBOLS** anahtarı görüntünün COFF sembol tablosunu görüntüler. **DUMPBIN** yardımcı programı hakkında daha fazla bilgi için bkz. [dumpbin başvurusu](../../build/reference/dumpbin-reference.md).

- Artımlı bağlamayı ve tam program iyileştirmesini geçici olarak devre dışı bırakın. Yeniden derlenme sırasında uygulama, içeri aktarılan simgeye başvuran işlevin adını içeren bir LNK4217 uyarı oluşturur. İçeri aktarılan sembolden `__declspec(dllimport)` bildirim değiştiricisini kaldırın ve artımlı bağlamayı veya tam program iyileştirmesini gerektiği şekilde yeniden etkinleştirin.

Son oluşturulan kod doğru şekilde davransa da, içeri aktarılan işlevi çağırmak için oluşturulan kod, işlevi doğrudan çağırmaktan daha az verimlidir. Bu uyarı [/clr](../../build/reference/clr-common-language-runtime-compilation.md) seçeneğini kullanarak derlerken görünmez.

Verileri içeri ve dışarı aktarma bildirimleri hakkında daha fazla bilgi için bkz. [dllexport, dllimport](../../cpp/dllexport-dllimport.md).

## <a name="example"></a>Örnek

Aşağıdaki iki modülün bağlanması LNK4049 oluşturacaktır. İlk modül, tek bir içe aktarılmış işlev içeren bir nesne dosyası oluşturur.

```cpp
// LNK4049a.cpp
// compile with: /c

__declspec(dllexport) int func()
{
   return 3;
}
```

İkinci modül, `main` işlevi içinde bu işleve bir çağrı ile birlikte ilk modülde dışarıya aktarılmış işleve bir iletme bildirimi içeren bir nesne dosyası oluşturur. Bu modülün ilk modülle bağlanması, LNK4049 oluşturacak. Uyarıyı çözmek için `__declspec(dllimport)` değiştiricisini bildirimden kaldırın.

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

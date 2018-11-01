---
title: Yalnızca Kaynak DLL Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- resource-only DLLs [C++], creating
- DLLs [C++], creating
ms.assetid: e6b1d4da-7275-467f-a58c-a0a8a5835199
ms.openlocfilehash: 9a31d4197e71fb6cf20a0ecfce778552357d7e06
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50612920"
---
# <a name="creating-a-resource-only-dll"></a>Yalnızca Kaynak DLL Oluşturma

Yalnızca kaynak DLL simgeler, bit eşlemler, dizeler ve iletişim kutuları gibi kaynakları içeren bir DLL'dir. Yalnızca kaynak DLL kullanarak aynı kümesi kaynakları birden çok programlar arasında paylaşmak için iyi bir yoludur. Ayrıca bir uygulamanın birden çok dil için yerelleştirilmiş kaynaklar sağlamak için en iyi yolu olan (bkz [MFC uygulamalarında yerelleştirilmiş kaynaklar: Uydu DLL'leri](../build/localized-resources-in-mfc-applications-satellite-dlls.md)).

Yalnızca kaynak DLL'i oluşturmak için yeni bir Win32 DLL (MFC olmayan) projesi oluşturun ve kaynaklarınızı projeye ekleyin.

- Win32 projesi içinde seçin **yeni proje** iletişim kutusu ve Win32 Proje Sihirbazı'nda bir DLL projesi türünü belirtin.

- DLL için kaynakları (örneğin, bir dize veya menü) içeren yeni bir kaynak betiği oluşturun ve .rc dosyasını kaydedin.

- Üzerinde **proje** menüsünde tıklatın **varolan öğeyi Ekle**ve ardından yeni bir .rc dosyasını projeye ekleyin.

- Belirtin [/NOENTRY](../build/reference/noentry-no-entry-point.md) bağlayıcı seçeneği. / NOENTRY bağlayıcı başvuru bağlamadan engeller `_main` DLL; yalnızca kaynak DLL'i oluşturmak için bu seçeneği gereklidir.

- DLL oluşturun.

Yalnızca kaynak DLL kullanan uygulama çağırmalıdır [LoadLibrary](../build/loadlibrary-and-afxloadlibrary.md) DLL'ye açıkça bağlanmak için. Kaynaklara erişmek için genel işlevlerini `FindResource` ve `LoadResource`, iş kaynağı herhangi bir türden veya aşağıdaki kaynağa özgü işlevleri birini çağırın:

- `FormatMessage`

- `LoadAccelerators`

- `LoadBitmap`

- `LoadCursor`

- `LoadIcon`

- `LoadMenu`

- `LoadString`

Uygulama çağırmalıdır `FreeLibrary` bunu bittiğinde kaynakları kullanarak.

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br/>
[Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)
---
title: Yalnızca Kaynak DLL Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- resource-only DLLs [C++], creating
- DLLs [C++], creating
ms.assetid: e6b1d4da-7275-467f-a58c-a0a8a5835199
ms.openlocfilehash: 7f0bad94cf3f126d27cc29567bd4f6c4a846bf1e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814390"
---
# <a name="creating-a-resource-only-dll"></a>Yalnızca Kaynak DLL Oluşturma

Yalnızca kaynak DLL simgeler, bit eşlemler, dizeler ve iletişim kutuları gibi kaynakları içeren bir DLL'dir. Yalnızca kaynak DLL kullanarak aynı kümesi kaynakları birden çok programlar arasında paylaşmak için iyi bir yoludur. Ayrıca bir uygulamanın birden çok dil için yerelleştirilmiş kaynaklar sağlamak için en iyi yolu olan (bkz [MFC uygulamalarında yerelleştirilmiş kaynaklar: Uydu DLL'leri](localized-resources-in-mfc-applications-satellite-dlls.md)).

Yalnızca kaynak DLL'i oluşturmak için yeni bir Win32 DLL (MFC olmayan) projesi oluşturun ve kaynaklarınızı projeye ekleyin.

- Win32 projesi içinde seçin **yeni proje** iletişim kutusu ve Win32 Proje Sihirbazı'nda bir DLL projesi türünü belirtin.

- DLL için kaynakları (örneğin, bir dize veya menü) içeren yeni bir kaynak betiği oluşturun ve .rc dosyasını kaydedin.

- Üzerinde **proje** menüsünde tıklatın **varolan öğeyi Ekle**ve ardından yeni bir .rc dosyasını projeye ekleyin.

- Belirtin [/NOENTRY](reference/noentry-no-entry-point.md) bağlayıcı seçeneği. / NOENTRY bağlayıcı başvuru bağlamadan engeller `_main` DLL; yalnızca kaynak DLL'i oluşturmak için bu seçeneği gereklidir.

- DLL oluşturun.

Yalnızca kaynak DLL kullanan uygulama çağırmalıdır [LoadLibrary](loadlibrary-and-afxloadlibrary.md) DLL'ye açıkça bağlanmak için. Kaynaklara erişmek için genel işlevlerini `FindResource` ve `LoadResource`, iş kaynağı herhangi bir türden veya aşağıdaki kaynağa özgü işlevleri birini çağırın:

- `FormatMessage`

- `LoadAccelerators`

- `LoadBitmap`

- `LoadCursor`

- `LoadIcon`

- `LoadMenu`

- `LoadString`

Uygulama çağırmalıdır `FreeLibrary` bunu bittiğinde kaynakları kullanarak.

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br/>
[Visual C++'ta DLL'ler](dlls-in-visual-cpp.md)

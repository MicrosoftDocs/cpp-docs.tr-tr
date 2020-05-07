---
title: Yalnızca kaynak DLL oluşturma
description: Visual Studio 'da yalnızca kaynak DLL oluşturma.
ms.date: 01/27/2020
helpviewer_keywords:
- resource-only DLLs [C++], creating
- DLLs [C++], creating
ms.assetid: e6b1d4da-7275-467f-a58c-a0a8a5835199
no-loc:
- noentry
ms.openlocfilehash: ef79de77e35cbef6acd4af1cec82a4edc1b7d105
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821349"
---
# <a name="creating-a-resource-only-dll"></a>Yalnızca kaynak DLL oluşturma

Yalnızca kaynak DLL, simgeler, bit eşlemler, dizeler ve iletişim kutuları gibi kaynakları içeren bir DLL 'dir. Yalnızca kaynak DLL kullanılması, birden fazla program arasında aynı kaynak kümesini paylaşmanın iyi bir yoludur. Ayrıca, birden çok dil için yerelleştirilmiş kaynaklarla bir uygulama sağlamak için iyi bir yoldur. Daha fazla bilgi için bkz. [MFC uygulamalarında yerelleştirilmiş kaynaklar: uydu dll 'leri](localized-resources-in-mfc-applications-satellite-dlls.md).

## <a name="create-a-resource-only-dll"></a>Yalnızca kaynak DLL oluşturma

Yalnızca kaynak DLL 'SI oluşturmak için yeni bir Windows DLL (MFC olmayan) projesi oluşturun ve kaynaklarınızı projeye ekleyin:

::: moniker range="vs-2015"

1. **Yeni proje** Iletişim kutusunda **Win32 projesi** ' ni seçin. Proje ve çözüm adlarını girip **Tamam**' ı seçin.

1. **Win32 uygulama Sihirbazı**'Nda **uygulama ayarları**' nı seçin. **DLL** **uygulama türünü** seçin. **Ek seçenekler**altında **boş proje**' yi seçin. Projenizi oluşturmak için **son** ' a tıklayın.

1. DLL 'nin kaynaklarını içeren yeni bir kaynak betiği oluşturun (örneğin, bir dize veya bir menü). `.rc` dosyasını kaydedin.

1. **Proje** menüsünde, **Varolan öğe Ekle**' yi seçin ve ardından yeni `.rc` dosyayı projeye ekleyin.

1. [/NOENTRY](reference/noentry-no-entry-point.md) bağlayıcı seçeneğini belirtin. `/NOENTRY`bağlayıcının DLL 'ye başvuru `_main` bağlamasını önler; Bu seçenek yalnızca kaynak DLL oluşturmak için gereklidir.

1. DLL 'yi oluşturun.

::: moniker-end
::: moniker range=">=vs-2017"

1. **Yeni proje** Iletişim kutusunda **Windows Masaüstü Sihirbazı** ' nı seçin ve **İleri ' yi**seçin. **Yeni projenizi yapılandırın** sayfasında, proje ve çözüm adlarını girin ve **Oluştur**' u seçin.

1. **Windows Masaüstü projesi** iletişim kutusunda, **dinamik bağlantı kitaplığının** **uygulama türünü** seçin. **Ek seçenekler**altında **boş proje**' yi seçin. Projenizi oluşturmak için **Tamam ' ı** seçin.

1. DLL 'nin kaynaklarını içeren yeni bir kaynak betiği oluşturun (örneğin, bir dize veya bir menü). `.rc` dosyasını kaydedin.

1. **Proje** menüsünde, **Varolan öğe Ekle**' yi seçin ve ardından yeni `.rc` dosyayı projeye ekleyin.

1. [/NOENTRY](reference/noentry-no-entry-point.md) bağlayıcı seçeneğini belirtin. `/NOENTRY`bağlayıcının DLL 'ye başvuru `_main` bağlamasını önler; Bu seçenek yalnızca kaynak DLL oluşturmak için gereklidir.

1. DLL 'yi oluşturun.

::: moniker-end

## <a name="use-a-resource-only-dll"></a>Yalnızca kaynak DLL kullanma

Yalnızca Resource DLL kullanan uygulama [LoadLibraryEx](loadlibrary-and-afxloadlibrary.md) ÖĞESINI veya dll 'e açık bir şekilde bağlanmak için ilgili işlevi çağırmalıdır. Kaynaklara erişmek için, genel işlevleri `FindResource` çağırın ve `LoadResource`her türlü kaynak üzerinde çalışır. Veya, kaynağa özgü aşağıdaki işlevlerden birini çağırın:

- `FormatMessage`

- `LoadAccelerators`

- `LoadBitmap`

- `LoadCursor`

- `LoadIcon`

- `LoadMenu`

- `LoadString`

Uygulama, kaynakları kullanmayı `FreeLibrary` bitirdiğinde çağırmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak dosyalarla çalışma](../windows/working-with-resource-files.md)\
[Visual Studio 'da C/C++ dll 'Leri oluşturma](dlls-in-visual-cpp.md)

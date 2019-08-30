---
title: Ek MSVC derleme araçları
ms.date: 08/28/2019
f1_keywords:
- c.build
helpviewer_keywords:
- builds [C++], C/C++ tools
- tools [C++], build
ms.assetid: 48d9daf4-6bbf-473a-8ce2-bf2923b69f80
ms.openlocfilehash: 53c7c2f8c162cd851b4612e75ba14b019d9cbd63
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177288"
---
# <a name="additional-msvc-build-tools"></a>Ek MSVC derleme araçları

Visual Studio, derleme çıkışını görüntülemek veya işlemek için aşağıdaki komut satırı yardımcı programlarını sağlar:

- [LIB. EXE](lib-reference.md) , ortak nesne dosyası biçimi (COFF) nesne dosyaları kitaplığını oluşturmak ve yönetmek için kullanılır. Ayrıca, dışa aktarma dosyaları oluşturmak ve dışarı aktarılan tanımlarına yönelik kitaplıkları içeri aktarmak için de kullanılabilir.

- [Editbin. ](editbin-reference.md)COFF ikili dosyalarını değiştirmek IÇIN exe kullanılır.

- [Dumpbin. EXE](dumpbin-reference.md) , COFF İkili dosyaları hakkında bilgi (örneğin, bir sembol tablosu) görüntüler.

- [NMAKE](nmake-reference.md) , makefiles okur ve yürütür.

- Hata arama yardımcı programı [ERRLOOK](value-edit-control.md), girilen değere göre bir sistem hatası iletisi veya modül hata iletisi alır.

- [XDCMake](xdcmake-reference.md). XML etiketleriyle işaretlenmiş belge açıklamalarını içeren kaynak kodu dosyalarını işlemek için bir araç.

- [Bscmake. EXE](bscmake-reference.md) (yalnızca geriye dönük uyumluluk için verilmiştir) programınızdaki semboller (sınıflar, işlevler, veriler, makrolar ve türler) hakkında bilgi içeren bir tarama bilgisi dosyası (. bsc) oluşturur. Bu bilgileri geliştirme ortamında Windows 'a gözatmanıza göre görüntüleyin. (Bir. bsc dosyası da geliştirme ortamında oluşturulabilir.)

Windows SDK Ayrıca RC dahil çeşitli derleme araçlarına sahiptir [. ](/windows/win32/menurc/resource-compiler)Böylece C++ derleyicinin iletişim kutuları, özellik sayfaları, bit eşlemler, dize tabloları gibi yerel Windows kaynaklarını derlemek için çağırdığı exe.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Başvurusu](c-cpp-building-reference.md)<br/>
[Düzenlenmiş Adlar](decorated-names.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)

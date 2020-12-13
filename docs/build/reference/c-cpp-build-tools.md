---
description: 'Daha fazla bilgi edinin: ek MSVC derleme araçları'
title: Ek MSVC derleme araçları
ms.date: 08/28/2019
f1_keywords:
- c.build
helpviewer_keywords:
- builds [C++], C/C++ tools
- tools [C++], build
ms.assetid: 48d9daf4-6bbf-473a-8ce2-bf2923b69f80
ms.openlocfilehash: 41395edcbc2f375b4173f2cff25cbcac581ee5d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182651"
---
# <a name="additional-msvc-build-tools"></a>Ek MSVC derleme araçları

Visual Studio, derleme çıkışını görüntülemek veya işlemek için aşağıdaki komut satırı yardımcı programlarını sağlar:

- [LIB.EXE](lib-reference.md) , ortak nesne dosyası BIÇIMI (COFF) nesne dosyaları kitaplığını oluşturmak ve yönetmek için kullanılır. Ayrıca, dışa aktarma dosyaları oluşturmak ve dışarı aktarılan tanımlarına yönelik kitaplıkları içeri aktarmak için de kullanılabilir.

- [EDITBIN.EXE](editbin-reference.md) COFF ikili dosyalarını değiştirmek için kullanılır.

- [DUMPBIN.EXE](dumpbin-reference.md) COFF İkili dosyaları ile ilgili bilgileri (sembol tablosu gibi) görüntüler.

- [NMAKE](nmake-reference.md) , makefiles okur ve yürütür.

- Hata arama yardımcı programı [ERRLOOK](value-edit-control.md), girilen değere göre bir sistem hatası iletisi veya modül hata iletisi alır.

- [XDCMake](xdcmake-reference.md). XML etiketleriyle işaretlenmiş belge açıklamalarını içeren kaynak kodu dosyalarını işlemek için bir araç.

- [BSCMAKE.EXE](bscmake-reference.md) (yalnızca geriye dönük uyumluluk için verilmiştir) programınızdaki semboller (sınıflar, işlevler, veriler, makrolar ve türler) hakkında bilgi içeren bir tarama bilgisi dosyası (. bsc) oluşturur. Bu bilgileri geliştirme ortamında Windows 'a gözatmanıza göre görüntüleyin. (Bir. bsc dosyası da geliştirme ortamında oluşturulabilir.)

Windows SDK Ayrıca, C++ derleyicisinin iletişim kutuları, özellik sayfaları, bit eşlemler, dize tabloları vb. gibi yerel Windows kaynaklarını derlemek için çağırdığı [RC.EXE](/windows/win32/menurc/resource-compiler)dahil olmak üzere çeşitli derleme araçlarına sahiptir.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Oluşturma Başvurusu](c-cpp-building-reference.md)<br/>
[Düzenlenmiş adlar](decorated-names.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)

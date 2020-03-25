---
title: Visual Studio 'da C++ projeler için MSBuild başvurusu
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild reference [C++]
ms.openlocfilehash: ec1285a760d438a94863181a1b099e6db153c268
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168908"
---
# <a name="msbuild-reference-for-c-projects"></a>C++ projeleri için MSBuild başvurusu

MSBuild, projeler dahil olmak üzere C++ Visual Studio 'daki tüm projeler için yerel derleme sistemidir. Visual Studio tümleşik geliştirme ortamında (IDE) bir proje oluşturduğunuzda, MSBuild. exe aracını çağırır, bu da. vcxproj proje dosyasını ve çeşitli. targets ve. props dosyalarını kullanır. Genel olarak, proje özelliklerini ayarlamak ve MSBuild 'i çağırmak için Visual Studio IDE 'nin kullanılması önemle önerilir. Proje dosyalarının el ile düzenlenmesiyle, doğru yapılmadığını önemli sorunlara yol açabilir.

MSBuild 'i komut satırından doğrudan kullanmak istiyorsanız, bkz. [komut satırından MSBuild 'ı kullanma](../msbuild-visual-cpp.md). Genel olarak MSBuild hakkında daha fazla bilgi için bkz. Visual Studio belgelerindeki [MSBuild](/visualstudio/msbuild/msbuild) .

## <a name="in-this-section"></a>Bu bölümde

[C++ projeleri için MSBuild iç işlevleri](msbuild-visual-cpp-overview.md)<br/>
Özelliklerin ve hedeflerin nasıl depolandığı ve tüketildiği hakkında bilgi.

[Derleme komutları ve özellikleri için genel makrolar](common-macros-for-build-commands-and-properties.md)<br/>
Yollar ve ürün sürümleri gibi özellikleri tanımlamak için kullanılabilen makroları (derleme zamanı sabitleri) açıklar.

[Projeler için C++ oluşturulan dosya türleri](file-types-created-for-visual-cpp-projects.md)<br/>
Farklı proje türleri için Visual Studio 'nun oluşturduğu çeşitli dosya türlerini açıklar.

[Visual Studio C++ proje şablonları](visual-cpp-project-types.md)<br>
İçin C++kullanılabilen MSBuild tabanlı proje türlerini açıklar.

[C++ yeni öğe şablonları](using-visual-cpp-add-new-item-templates.md)<br>
Visual Studio projesine ekleyebileceğiniz kaynak dosyaları ve diğer öğeleri açıklar.

[Ön derlenmiş üstbilgi dosyaları](../creating-precompiled-header-files.md) Önceden derlenmiş üstbilgi dosyalarını kullanma ve derleme sürelerini hızlandırmak için özel ön derlenmiş kodunuzu oluşturma.

[Visual Studio proje özelliği başvurusu](property-pages-visual-cpp.md)<br/>
Visual Studio IDE 'de ayarlanan proje özellikleri için başvuru belgeleri.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Başvurusu](c-cpp-building-reference.md)

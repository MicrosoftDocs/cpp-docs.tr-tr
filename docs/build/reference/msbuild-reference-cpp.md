---
title: Visual Studio'da C++ projeleri için MSBuild başvurusu
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild reference [C++]
ms.openlocfilehash: 96987a252d12f718025dd55deecad5c6bac26872
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336208"
---
# <a name="msbuild-reference-for-c-projects"></a>C++ projeleri için MSBuild başvurusu

MSBuild, Visual Studio'daki C++ projeleri de dahil olmak üzere tüm projeler için yerel yapı sistemidir. Visual Studio tümleşik geliştirme ortamında (IDE) bir proje oluşturduğunuzda, .vcxproj proje dosyasını ve çeşitli .hedefleri ve .props dosyalarını tüketen msbuild.exe aracını çağırır. Genel olarak, proje özelliklerini ayarlamak ve MSBuild'i çağırmak için Visual Studio IDE'yi kullanmanızı şiddetle öneririz. Proje dosyalarını el ile düzenlemek, doğru yapılmazsa ciddi sorunlara yol açabilir.

Bazı nedenlerden dolayı MSBuild'i doğrudan komut satırından kullanmak istiyorsanız, [bkz.](../msbuild-visual-cpp.md) Genel olarak MSBuild hakkında daha fazla bilgi için Visual Studio belgelerinde [MSBuild'e](/visualstudio/msbuild/msbuild) bakın.

## <a name="in-this-section"></a>Bu bölümde

[C++ projeleri için MSBuild iç işlevleri](msbuild-visual-cpp-overview.md)<br/>
Özelliklerin ve hedeflerin nasıl depolanıp tüketilmeleri hakkında bilgi.

[Yapı komutları ve özellikleri için ortak makrolar](common-macros-for-build-commands-and-properties.md)<br/>
Yollar ve ürün sürümleri gibi özellikleri tanımlamak için kullanılabilecek makroları (derleme zamanı sabitlerini) açıklar.

[C++ projeleri için oluşturulan dosya türleri](file-types-created-for-visual-cpp-projects.md)<br/>
Visual Studio'nun farklı proje türleri için oluşturduğu çeşitli dosya türlerini açıklar.

[Visual Studio C++ proje şablonları](visual-cpp-project-types.md)<br>
C++'da kullanılabilen MSBuild tabanlı proje türlerini açıklar.

[C++ yeni öğe şablonları](using-visual-cpp-add-new-item-templates.md)<br>
Visual Studio projesine ekleyebileceğiniz kaynak dosyaları ve diğer öğeleri açıklar.

[Önceden derlenmiş üstbilgi dosyaları](../creating-precompiled-header-files.md) Önceden derlenmiş üstbilgi dosyalarını nasıl kullanacağınız ve oluşturma sürelerini hızlandırmak için kendi özel önceden derlenmiş kodunuzu nasıl oluşturabilirsiniz.

[Visual Studio proje özellik başvurusu](property-pages-visual-cpp.md)<br/>
Visual Studio IDE'de ayarlanan proje özellikleri için başvuru belgeleri.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Oluşturma Başvurusu](c-cpp-building-reference.md)

---
description: 'Daha fazla bilgi edinin: C++ projeleri için MSBuild başvurusu'
title: Visual Studio 'da C++ projeleri için MSBuild başvurusu
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild reference [C++]
ms.openlocfilehash: 898757c8b7f1427c36e68a7227ec145abab8d078
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190620"
---
# <a name="msbuild-reference-for-c-projects"></a>C++ projeleri için MSBuild başvurusu

MSBuild, C++ projeleri de dahil olmak üzere Visual Studio 'daki tüm projeler için yerel derleme sistemidir. Visual Studio tümleşik geliştirme ortamında (IDE) bir proje oluşturduğunuzda, bu msbuild.exe aracı çağırır, bu da. vcxproj proje dosyasını ve çeşitli. targets ve. props dosyalarını kullanır. Genel olarak, proje özelliklerini ayarlamak ve MSBuild 'i çağırmak için Visual Studio IDE 'nin kullanılması önemle önerilir. Proje dosyalarının el ile düzenlenmesiyle, doğru yapılmadığını önemli sorunlara yol açabilir.

MSBuild 'i komut satırından doğrudan kullanmak istiyorsanız, bkz. [komut satırından MSBuild 'ı kullanma](../msbuild-visual-cpp.md). Genel olarak MSBuild hakkında daha fazla bilgi için bkz. Visual Studio belgelerindeki [MSBuild](/visualstudio/msbuild/msbuild) .

## <a name="in-this-section"></a>Bu bölümde

[C++ projeleri için MSBuild iç işlevleri](msbuild-visual-cpp-overview.md)<br/>
Özelliklerin ve hedeflerin nasıl depolandığı ve tüketildiği hakkında bilgi.

[Derleme komutları ve özellikleri için genel makrolar](common-macros-for-build-commands-and-properties.md)<br/>
Yollar ve ürün sürümleri gibi özellikleri tanımlamak için kullanılabilen makroları (derleme zamanı sabitleri) açıklar.

[C++ projeleri için oluşturulan dosya türleri](file-types-created-for-visual-cpp-projects.md)<br/>
Farklı proje türleri için Visual Studio 'nun oluşturduğu çeşitli dosya türlerini açıklar.

[Visual Studio C++ proje şablonları](visual-cpp-project-types.md)<br>
C++ için kullanılabilen MSBuild tabanlı proje türlerini açıklar.

[C++ yeni öğe şablonları](using-visual-cpp-add-new-item-templates.md)<br>
Visual Studio projesine ekleyebileceğiniz kaynak dosyaları ve diğer öğeleri açıklar.

[Ön derlenmiş üstbilgi dosyaları](../creating-precompiled-header-files.md) Önceden derlenmiş üstbilgi dosyalarını kullanma ve derleme sürelerini hızlandırmak için özel ön derlenmiş kodunuzu oluşturma.

[Visual Studio proje özelliği başvurusu](property-pages-visual-cpp.md)<br/>
Visual Studio IDE 'de ayarlanan proje özellikleri için başvuru belgeleri.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Oluşturma Başvurusu](c-cpp-building-reference.md)

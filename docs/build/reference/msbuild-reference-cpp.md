---
title: Visual Studio'da C++ projeleri için MSBuild başvurusu
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild reference [C++]
ms.openlocfilehash: b6ec6b5d276cb7104cf61c229476596d2a2a7684
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320935"
---
# <a name="msbuild-reference-for-c-projects"></a>C++ projeleri için MSBuild başvurusu

MSBuild, Visual Studio'da C++ projeleri dahil olmak üzere, tüm projeler için yerel derleme sistemidir. Visual Studio tümleşik geliştirme ortamında (IDE) proje oluşturduğunuzda, .vcxproj proje dosyasını ve çeşitli .targets ve .props dosyaları sırayla tüketir msbuild.exe aracını çağırır. Genel olarak, proje özellikleri ayarlamak ve MSBuild'ı çağırmak için Visual Studio IDE'yi kullanmanızı öneririz. Proje dosyalarını el ile düzenleme doğru yapılmaması durumunda ciddi sorunlara yol açabilir.

Herhangi bir nedenden dolayı doğrudan komut satırında MSBuild kullanmak istiyorsanız, bkz. [kullanın MSBuild komut satırından](../msbuild-visual-cpp.md). Genel olarak, MSBuild hakkında daha fazla bilgi için bkz [MSBuild](/visualstudio/msbuild/msbuild) Visual Studio belgelerinde.

## <a name="in-this-section"></a>Bu bölümde

[C++ projeleri için MSBuild iç işlevleri](msbuild-visual-cpp-overview.md)<br/>
Nasıl özellikleri ve hedefler depolanan tüketilen ve hakkında bilgiler.

[Derleme komutları ve özellikleri için genel makrolar](common-macros-for-build-commands-and-properties.md)<br/>
Yollar ve ürün sürümleri gibi özelliklerini tanımlamak için kullanılan makrolar (derleme zamanı sabitleri) açıklar.

[C++ projeleri için oluşturulan dosya türleri](file-types-created-for-visual-cpp-projects.md)<br/>
Visual Studio oluşturan dosyaları farklı proje türleri için çeşitli türlerde açıklar.

[Visual Studio C++ proje şablonları](visual-cpp-project-types.md)<br>
C++ için kullanılabilir olan MSBuild tabanlı proje türlerini tanımlar.

[C++ yeni öğe şablonları](using-visual-cpp-add-new-item-templates.md)<br>
Kaynak dosyaları ve Visual Studio projesine eklediğiniz diğer öğeleri açıklar.

[Önceden derlenmiş üst bilgi dosyaları](../creating-precompiled-header-files.md) önceden derlenmiş kod oluşturma sürelerini hızlandırmak için önceden derlenmiş üst bilgi dosyaları ve kendi özel oluşturmak nasıl kullanılacağını nasıl.

[Visual Studio Proje Özellik Başvurusu](property-pages-visual-cpp.md)<br/>
Proje özellikleri, Visual Studio IDE içinde ayarlamak için başvuru belgeleri.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Başvurusu](c-cpp-building-reference.md)
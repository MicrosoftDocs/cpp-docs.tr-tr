---
title: C/C++ Programları Bildirim Üretimini Anlama
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
ms.assetid: a1f24221-5b09-4824-be48-92eae5644b53
ms.openlocfilehash: d4dceec94a8868ed9b6d744a9f481825bf6af58a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660453"
---
# <a name="understanding-manifest-generation-for-cc-programs"></a>C/C++ Programları Bildirim Üretimini Anlama

A [bildirim](https://msdn.microsoft.com/library/aa375365) dış bir XML dosyasına veya bir kaynak olabilir bir XML belgesi bir uygulama ya da derleme katıştırılır. Bildirimi bir [yalıtılmış uygulama](/windows/desktop/SbsCs/isolated-applications) adları ve paylaşılan yan yana derlemeler için uygulaması bağlama çalışma zamanında sürümlerini yönetmek için kullanılır. Yan yana derlemenin bildirimi, adları, sürümlerini, kaynaklarını ve diğer derlemeler bağımlılıklarını belirtir.

Yalıtılmış bir uygulama veya bir yan yana derleme için bir bildirim oluşturmak için iki yolu vardır. İlk olarak, derleme yazarı kurallara ve adlandırma gereksinimlerini bildirim dosyasını el ile oluşturabilirsiniz. Bir program, CRT, MFC, ATL veya diğerleri gibi Visual C++ derlemeler yalnızca bağımlı olması durumunda, alternatif olarak, ardından bir bildirimi otomatik olarak bağlayıcı tarafından oluşturulabilir.

Visual C++ kitaplıklarının üstbilgileri derleme bilgilerini içeren ve uygulama kodunda kitaplıkları eklendiğinde bu derleme bilgileri bağlayıcı tarafından son ikili yönelik bir bildirim oluşturmak için kullanılır. Bağlayıcı, ikili içinde bildirim dosyası ekleme değildir ve yalnızca bir dış dosya olarak bildirimde oluşturabilir. Dış dosya bir bildirim olması için tüm senaryoları çalışmayabilir. Örneğin, özel derlemeler bildirimleri gömülü önerilir. Nmake Kodu derlemek için kullananlar gibi komut satırı derlemelerinde bildirim aracını kullanarak bir bildirim eklenebilir; Daha fazla bilgi için [Manifest Generation komut satırında](../build/manifest-generation-at-the-command-line.md). Visual Studio'da oluşturma sırasında bir listesi için bildirim Aracı'nda bir özelliği ayarlayarak eklenebilir **proje özellikleri** iletişim; bkz: [Visual Studio'da bildirim oluşturma](../build/manifest-generation-in-visual-studio.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Yalıtılmış Uygulama ve Yan Yana Derleme Kavramları](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
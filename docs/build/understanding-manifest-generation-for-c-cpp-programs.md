---
description: 'Hakkında daha fazla bilgi edinin: C/C++ programları için bildirim oluşturmayı anlama'
title: C/C++ Programları Bildirim Üretimini Anlama
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
ms.assetid: a1f24221-5b09-4824-be48-92eae5644b53
ms.openlocfilehash: 78169dd6d8185e1ae8470dea93ab145fc05dbc7b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277277"
---
# <a name="understanding-manifest-generation-for-cc-programs"></a>C/C++ Programları Bildirim Üretimini Anlama

[Bildirim](/windows/win32/sbscs/manifests) , BIR dış XML dosyası veya bir uygulama ya da derleme içine katıştırılmış kaynak olabılecek bir XML belgesidir. [Yalıtılmış bir uygulamanın](/windows/win32/SbsCs/isolated-applications) bildirimi, uygulamanın çalışma zamanında bağlanması gereken paylaşılan yan yana derlemelerin adlarını ve sürümlerini yönetmek için kullanılır. Yan yana derlemenin bildirimi, adları, sürümleri, kaynakları ve diğer derlemelerdeki bağımlılıklarını belirtir.

Yalıtılmış bir uygulama veya yan yana derleme için bir bildirim oluşturmanın iki yolu vardır. İlk olarak, derlemenin yazarı kuralları ve adlandırma gereksinimlerini izleyerek el ile bir bildirim dosyası oluşturabilir. Alternatif olarak, bir program yalnızca CRT, MFC, ATL veya diğerleri gibi Visual C++ derlemelere bağımlıysa, bir bildirim bağlayıcı tarafından otomatik olarak oluşturulabilir.

Visual C++ kitaplıklarının üstbilgileri derleme bilgilerini içerir ve kitaplıklar uygulama koduna dahil edildiğinde, bu derleme bilgileri bağlayıcı tarafından son ikiliye yönelik bir bildirim oluşturmak için kullanılır. Bağlayıcı, bildirim dosyasını ikili dosya içine eklemez ve yalnızca bir dış dosya olarak bildirim oluşturabilir. Bir bildirimin dış dosya olarak bulunması, tüm senaryolarda çalışmayabilir. Örneğin, özel derlemelerin katıştırılmış bildirimlere sahip olması önerilir. Kod oluşturmak için nmake 'i kullananlar gibi komut satırı Derlemeleriyle, bildirim aracı kullanılarak bir bildirim katıştırılabilir. daha fazla bilgi için bkz. [komut satırında bildirim oluşturma](manifest-generation-at-the-command-line.md). Visual Studio 'da derleme yaparken, bir bildirim, **Proje özellikleri** iletişim kutusunda bildirim aracı için bir özellik ayarlanarak gömülebilir. bkz. [Visual Studio 'Da bildirim oluşturma](manifest-generation-in-visual-studio.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yalıtılmış uygulamalar ve yan yana derlemeler için kavramlar](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[C/C++ yalıtılmış uygulamaları ve yan yana derlemeler oluşturma](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)

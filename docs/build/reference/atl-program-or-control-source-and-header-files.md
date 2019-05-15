---
title: ATL Programı veya Denetim Kaynağı ve Başlık Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
ms.openlocfilehash: 5c1e5fc111b38fc9e4173598f11fbad7a658d755
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707505"
---
# <a name="atl-program-or-control-source-and-header-files"></a>ATL Programı veya Denetim Kaynağı ve Başlık Dosyaları

Oluşturduğunuz proje için belirlediğiniz seçeneklere bağlı olarak Visual Studio'da bir ATL projesi oluşturduğunuzda, aşağıdaki dosyalar oluşturulur.

Bu dosyaların tümünün bulunan *Projname* dizin ve üst bilgi dosyaları (.h) klasör ya da Çözüm Gezgini'nde klasörü kaynak dosyaları (.cpp).

|Dosya adı|Açıklama|
|---------------|-----------------|
|*PROJNAME*.h|C++ arabirimi tanımları ve GUID bildirimlerini ATLSample.idl içinde tanımlanan öğeleri içeren ana içerme dosyası. Derleme sırasında MIDL tarafından yeniden oluşturulur.|
|*PROJNAME*.cpp|Ana program kaynak dosyası. İşlem sunucusu için DLL dışarı aktarmaları uygulaması ve uygulamasını içeren `WinMain` yerel sunucu için. Bir hizmet için bu ayrıca tüm hizmet yönetim işlevlerini uygular.|
|Kaynak.h|Kaynak dosyası için üst bilgi dosyası.|
|StdAfx.cpp|StdAfx.h ve Atlimpl.cpp dosyaları içerir.|
|StdAfx.h|ATL üstbilgi dosyalarını içerir.|

## <a name="see-also"></a>Ayrıca bkz.

[Oluşturulan türleri için Visual Studio dosya C++ projeleri](file-types-created-for-visual-cpp-projects.md)<br>
[MFC Programı veya Denetim Kaynağı ve Başlık Dosyaları](mfc-program-or-control-source-and-header-files.md)<br>
[CLR projeleri](files-created-for-clr-projects.md)

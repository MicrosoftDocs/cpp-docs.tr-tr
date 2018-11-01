---
title: ATL Programı veya Denetim Kaynağı ve Başlık Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
ms.openlocfilehash: dc2fc7a81d2d32e6bc89e1c10b8fe090650db2ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630587"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++ Projeleri için Oluşturulan Dosya Türleri](../ide/file-types-created-for-visual-cpp-projects.md)<br>
[MFC Programı veya Denetim Kaynağı ve Başlık Dosyaları](../ide/mfc-program-or-control-source-and-header-files.md)<br>
[CLR projeleri](../ide/files-created-for-clr-projects.md)
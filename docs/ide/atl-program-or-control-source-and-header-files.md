---
title: ATL programı veya Denetim Kaynağı ve başlık dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95fa6fa506e4f471b90d39659b0908e2755b72b0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398709"
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
---
description: 'Daha fazla bilgi edinin: ATL programı veya denetim kaynağı ve üstbilgi dosyaları'
title: ATL Programı veya Denetim Kaynağı ve Başlık Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
ms.openlocfilehash: 05407e74931112a1680fb103c20c4a2022185026
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182794"
---
# <a name="atl-program-or-control-source-and-header-files"></a>ATL Programı veya Denetim Kaynağı ve Başlık Dosyaları

Oluşturduğunuz proje için belirlediğiniz seçeneklere bağlı olarak, Visual Studio 'da bir ATL projesi oluşturduğunuzda aşağıdaki dosyalar oluşturulur.

Bu dosyaların tümü, *ProjName* dizininde ve Çözüm Gezgini Içindeki üstbilgi dosyaları (. h dosyaları) klasöründe veya kaynak dosyaları (. cpp dosyaları) klasöründe bulunur.

|Dosya adı|Açıklama|
|---------------|-----------------|
|*ProjName*. h|ATLSample. IDL içinde tanımlanan öğelerin C++ arabirim tanımlarını ve GUID bildirimlerini içeren ana ekleme dosyası. Derleme sırasında MıDL tarafından yeniden oluşturulur.|
|*ProjName*. cpp|Ana program kaynak dosyası. DLL 'nin dışarı aktarımlarının bir işlem içi sunucu ve `WinMain` yerel sunucu için uygulamasını içerir. Bir hizmet için, bu ek olarak tüm hizmet yönetimi işlevlerini de uygular.|
|Kaynak.h|Kaynak dosyası için üst bilgi dosyası.|
|Stbafx. cpp|, Stbafx. h ve Atlımpl. cpp dosyalarını içerir.|
|Stbafx. h|ATL üstbilgi dosyalarını içerir.|

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio C++ projeleri için oluşturulan dosya türleri](file-types-created-for-visual-cpp-projects.md)<br>
[MFC programı veya denetim kaynağı ve üstbilgi dosyaları](mfc-program-or-control-source-and-header-files.md)<br>
[CLR projeleri](files-created-for-clr-projects.md)

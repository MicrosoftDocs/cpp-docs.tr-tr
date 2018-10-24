---
title: Sağlayıcınızda hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], providers
- OLE DB providers, debugging
- Visual C++ debugger, debugging providers
- Visual C++ debugger
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fc4461bb29bb9b9c706177c4dcd2134d37d697e0
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2018
ms.locfileid: "49989911"
---
# <a name="debugging-your-provider"></a>Sağlayıcınızda Hata Ayıklama

Sağlayıcınızda hata ayıklamanın iki yolu vardır:  
  
- Sağlayıcıları işlemde oluşturulduğundan, normalde sağlayıcı içine adımlama ve OLE DB Tüketici Şablonları kullanarak bazı tüketici kodu oluşturabilirsiniz.  
  
- Visual C++ ile birlikte gelen ITEST yardımcı programını kullanabilirsiniz.  
  
## <a name="to-use-the-itest-utility"></a>ITEST yardımcı programını kullanmak için  
  
1. Sağlayıcı projesini açın.  
  
1. Üzerinde **projeleri** menüsünde tıklatın **ayarları**.  
  
1. İçinde **özellik sayfaları** iletişim kutusu, tıklayın **hata ayıklama** sekmesi.  
  
1. İçinde **hata ayıklama oturumu için yürütülebilir** kutusunda, ITEST uygulamayı seçin.  
  
1. Kesme noktaları ayarlayın ve her zaman olduğu gibi hata ayıklama.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)
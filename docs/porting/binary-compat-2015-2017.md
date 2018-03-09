---
title: "Visual Studio 2015 ve Visual Studio 2017 C++ ikili uyumluluğu | Microsoft Docs"
ms.custom: 
ms.date: 09/21/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f534432fbf7ff723cac1448bc3a26474f3b323bb
ms.sourcegitcommit: c770a343def04ae77522708387c3f7c470e49969
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2017"></a>Visual Studio 2015 ve Visual Studio 2017 C++ ikili uyumluluğu


Visual Studio'nun önceki sürümleri nesne dosyaları (OBJs), statik kitaplıklar (kitaplıklar), dinamik kitaplıklarını (DLL'ler) ve derleyici araç takımını ve çalışma zamanı kitaplıkları farklı sürümleri kullanılarak oluşturulmuş yürütülebilir dosyalar (exe) arasında ikili uyumluluğu değildi garanti. Bu Visual Studio 2017 değişti. Visual Studio 2015 ve Visual Studio 2017'de, C++ araç takımını ana 14 (v140 Visual Studio 2015 ve Visual Studio 2017 v141) sayısıdır. Çalışma zamanı kitaplıkları ve derleyici her iki sürümü ile derlenmiş uygulamalar--en için--ikili uyumlu parçasıdır olgu yansıtır. Bu, örneğin, bir DLL Visual Studio 2017 ' oluşturabilir ve Visual Studio 2015 ile derlenen bir uygulamadan kullanmak veya 2015 araç setini kullanarak yerleşik uygulamanız ile Visual Studio 2017 yeniden dağıtılabilir kitaplıkları kullanabilirsiniz, anlamına gelir.  

Bu kural için iki özel durum vardır. Bu durumlarda ikili uyumluluğu garanti edilmez:  

1) Ne zaman statik kitaplıklar veya nesne dosyaları /GL derleyici anahtarıyla derlenir.  

2) Sürümü derlemek ve uygulama bağlamak için kullanılan araç takımı büyük bir araç takımı ile oluşturulan kitaplıkları kullanırken. Örneğin, derlenmiş ve araç takımı 19.12 ile ilişkili olan bir program ile 19,0 yukarı 19.12 derlenen kitaplıklarını kullanabilir. 19.x bağlama Visual Studio 2013 tarafından üretilen kitaplıklarla programları veya önceki sürümleri desteklenmez.


## <a name="see-also"></a>Ayrıca Bkz.  

[Visual C++ değişiklik geçmişi](..\porting\visual-cpp-change-history-2003-2015.md)



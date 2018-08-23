---
title: Visual Studio 2015 ve Visual Studio 2017 arasındaki C++ ikili uyumluluğu | Microsoft Docs
ms.custom: ''
ms.date: 09/21/2017
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d7f96206288828a3e38422786585b3d66787860d
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2018
ms.locfileid: "42464580"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2017"></a>Visual Studio 2015 ve Visual Studio 2017 arasındaki C++ ikili uyumluluğu

Visual Studio'nun önceki sürümlerinde, nesne dosyaları (OBJs), statik kitaplıklar (kitaplıklar), dinamik kitaplıkları (DLL'ler) ve derleyici araç takımı ve çalışma zamanı kitaplıkların farklı sürümleri kullanılarak oluşturulan yürütülebilir dosyaların (EXE'ler) arasında ikili uyumluluğu değildi. garanti ediyoruz. Bu, Visual Studio 2017'de değişti. Visual Studio 2015 ve Visual Studio 2017'de, C++ araç takımı büyük 14 (v140 için Visual Studio 2015 ve Visual Studio 2017 v141) sayısıdır. Bu, hem çalışma zamanı kitaplıklarının ve derleyicinin ya da bir sürüm ile derlenmiş uygulamaları--en için--uyumlu ikili parçasıdır olgu yansıtır. Bu, örneğin, bir DLL Visual Studio 2017'de oluşturabilir ve Visual Studio 2015 ile derlenmiş bir uygulamadan kullanma veya bir 2015 araç kullanılarak oluşturulan uygulamanızla birlikte Visual Studio 2017 yeniden dağıtılabilir kitaplıklarını kullanın, anlamına gelir.  

Bu kural için iki istisna mevcuttur. Bu gibi durumlarda ikili uyumluluğu garanti edilmez:  

1. Ne zaman statik kitaplıklar veya nesne dosyalarına derlenir ile `/GL` derleyici anahtarı.  

2. Sürümü derlemek ve uygulamayı bağlamak için kullanılan araç kümesini büyük bir araç takımı ile oluşturulmuş kitaplıkları tüketildiğinde. Örneğin, derlenmiş ve 19.12 araç takımı ile ilişkili olan bir program ile 19.0 yukarı 19.12 ile derlenen kitaplıkları kullanabilir. 19.x bağlama, Visual Studio 2013'ün tarafından üretilen kitaplıklar programları veya daha önce desteklenmiyor.

## <a name="see-also"></a>Ayrıca Bkz.  

[Visual C++ değişiklik geçmişi](..\porting\visual-cpp-change-history-2003-2015.md)
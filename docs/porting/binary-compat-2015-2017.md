---
title: Visual Studio 2015 ve Visual Studio 2017 arasındaki C++ ikili uyumluluğu | Microsoft Docs
ms.custom: ''
ms.date: 09/24/2018
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
ms.openlocfilehash: 6f6d81f5cdce8955194985f66863940b97e32d40
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065531"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2017"></a>Visual Studio 2015 ve Visual Studio 2017 arasındaki C++ ikili uyumluluğu

Visual Studio'nun önceki sürümlerinde, nesne dosyaları (OBJs), statik kitaplıklar (kitaplıklar), dinamik kitaplıkları (DLL'ler) ve derleyici araç takımı ve çalışma zamanı kitaplıkların farklı sürümleri kullanılarak oluşturulan yürütülebilir dosyaların (EXE'ler) arasında ikili uyumluluğu değildi. garanti ediyoruz. Bu, Visual Studio 2017'de değişti. Visual Studio 2015 ve Visual Studio 2017'de, C++ araç takımı büyük 14 (v140 için Visual Studio 2015 ve Visual Studio 2017 v141) sayısıdır. Bu, hem çalışma zamanı kitaplıklarının ve derleyicinin ya da bir sürüm ile derlenmiş uygulamaları--en için--uyumlu ikili parçasıdır olgu yansıtır. Bu, örneğin, Visual Studio 2015'te bir DLL dosyanız varsa, Visual Studio 2017 ile oluşturulmuş bir uygulamadan kullanmak için derlemeniz yok anlamına gelir.

Bu kural için iki istisna mevcuttur. Bu gibi durumlarda ikili uyumluluğu garanti edilmez:

1. Ne zaman statik kitaplıklar veya nesne dosyalarına derlenir ile `/GL` derleyici anahtarı.

2. Sürümü derlemek ve uygulamayı bağlamak için kullanılan araç kümesini büyük bir araç takımı ile oluşturulmuş kitaplıkları tüketildiğinde. Örneğin, derlenmiş ve 19.12 derleyici sürümü ile ilişkili olan bir program ile 19.0 yukarı 19.12 ile derlenen kitaplıkları kullanabilir. Ayrıca, Visual Studio 2015 ve Visual Studio 2017 arasında ikili uyumluluğu yalnızca var; Visual Studio 2013 veya önceki üretilen kitaplıklarıyla 19.x programları bağlama desteklenmiyor.

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++ değişiklik geçmişi](..\porting\visual-cpp-change-history-2003-2015.md)

---
title: Visual Studio 2015 ve Visual Studio 2017 arasındaki C++ ikili uyumluluğu
ms.date: 09/24/2018
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: d0291ef75bda2e4da994e40ad55d94ae1042e57e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62205510"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2017"></a>Visual Studio 2015 ve Visual Studio 2017 arasındaki C++ ikili uyumluluğu

Visual Studio'nun önceki sürümlerinde, nesne dosyaları (OBJs), statik kitaplıklar (kitaplıklar), dinamik kitaplıkları (DLL'ler) ve derleyici araç takımı ve çalışma zamanı kitaplıkların farklı sürümleri kullanılarak oluşturulan yürütülebilir dosyaların (EXE'ler) arasında ikili uyumluluğu değildi. garanti ediyoruz. Bu, Visual Studio 2017'de değişti. Visual Studio 2015 ve Visual Studio 2017'de, C++ araç takımı büyük 14 (v140 için Visual Studio 2015 ve Visual Studio 2017 v141) sayısıdır. Bu, hem çalışma zamanı kitaplıklarının ve derleyicinin ya da bir sürüm ile derlenmiş uygulamaları--en için--uyumlu ikili parçasıdır olgu yansıtır. Bu, örneğin, Visual Studio 2015'te bir DLL dosyanız varsa, Visual Studio 2017 ile oluşturulmuş bir uygulamadan kullanmak için derlemeniz yok anlamına gelir.

Bu kural için iki istisna mevcuttur. Bu gibi durumlarda ikili uyumluluğu garanti edilmez:

1. Ne zaman statik kitaplıklar veya nesne dosyalarına derlenir ile `/GL` derleyici anahtarı.

2. Sürümü derlemek ve uygulamayı bağlamak için kullanılan araç kümesini büyük bir araç takımı ile oluşturulmuş kitaplıkları tüketildiğinde. Örneğin, derlenmiş ve 19.12 derleyici sürümü ile ilişkili olan bir program ile 19.0 yukarı 19.12 ile derlenen kitaplıkları kullanabilir. Ayrıca, Visual Studio 2015 ve Visual Studio 2017 arasında ikili uyumluluğu yalnızca var; Visual Studio 2013 veya önceki üretilen kitaplıklarıyla 19.x programları bağlama desteklenmiyor.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ değişiklik geçmişi](../porting/visual-cpp-change-history-2003-2015.md)

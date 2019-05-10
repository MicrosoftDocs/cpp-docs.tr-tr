---
title: C++Visual Studio 2015 ve Visual Studio 2019 ikili uyumluluğu
ms.date: 05/03/2019
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: 052874eb9273ee9a9ce1695ffdadedd9911673e1
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65449039"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2019"></a>C++Visual Studio 2015 ve Visual Studio 2019 ikili uyumluluğu

Visual Studio 2013 ve önceki sürümlerinde, nesne dosyaları (OBJs), statik kitaplıklar (kitaplıklar), dinamik kitaplıkları (DLL'ler) ve derleyici araç takımı ve çalışma zamanı kitaplıkların farklı sürümleri kullanılarak oluşturulan yürütülebilir dosyaların (EXE'ler) arasında ikili uyumluluğu garanti edilmez. 

Visual Studio 2015 ve sonraki sürümlerinde, C++ araç takımı büyük bir sayıdır (v140 Visual Studio 2015 için Visual Studio 2017 v141 yanı sıra, Visual Studio 2019 için v142) 14. Bu, hem çalışma zamanı kitaplıkları hem de ya da derleyici sürümüyle derlenmiş uygulamalar ikili uyumlu olması, yansıtır. Bu, Visual Studio 2015 ile oluşturulan bir üçüncü taraf kitaplığı varsa, Visual Studio 2017 veya Visual Studio 2019 ile oluşturulan bir uygulamadan kullanmak için derlemeniz yok anlamına gelir.

Bu kuralın tek özel durumu olan statik kitaplıkların veya ile derlenmiş nesne dosyaları `/GL` derleyici anahtarı ikili uyumlu değildir. 

Desteklenen sürümler MSVC araç, görsel olduğunda bu, farklı ile oluşturulan ikili dosyaları kesinlikle karıştırmayın C++ yeniden dağıtılabilir uygulama çalıştırmalarınızı sürümlerinin herhangi birinin uygulamanız veya tüm kitaplıkları oluşturmak için kullanılan araç takımı önce olamaz kullanır. 

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ değişiklik geçmişi](../porting/visual-cpp-change-history-2003-2015.md)

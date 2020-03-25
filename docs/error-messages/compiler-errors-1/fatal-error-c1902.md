---
title: Önemli Hata C1902
ms.date: 11/04/2016
f1_keywords:
- C1902
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
ms.openlocfilehash: 10a411dfc942498a98959d9a23cb42dfb93cf2ae
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202832"
---
# <a name="fatal-error-c1902"></a>Önemli Hata C1902

Program veritabanı yöneticisi uyuşmazlığı; Lütfen yüklemenizi denetleyin

Bir program veritabanı dosyası (. pdb), bir mspdb*XXX*. dll ' nin sisteminizde bulunan derleyicisinden daha yeni bir sürümü kullanılarak oluşturulmuştur. Bu hata genellikle mspdbsrv. exe veya mspdbcore. dll dosyasının eksik olduğunu veya mspdb*XXX*. dll ' den farklı sürümlere sahip olduğunu gösterir. (Mspdb*XXX*. dll dosya adı içindeki *XXX* yer tutucusu her ürün sürümüyle birlikte değişir. Örneğin, Visual Studio 2015 ' de dosya adı mspdb140. dll ' dir.)

System üzerinde mspdbsrv. exe, mspdbcore. dll ve mspdb*XXX*. dll ' nin eşleşen sürümlerinin yüklü olduğundan emin olun. Eşleşmeyen sürümlerin, hedef platformunuzun derleyicisini ve bağlantı araçlarını içeren dizine kopyalanmadığından emin olun. Örneğin, dosyaları kopyalanmış olabilirsiniz. bu sayede, **Path** ortam değişkenini uygun şekilde ayarlamadan derleyici veya bağlantı aracını komut isteminden çağırabilirsiniz.

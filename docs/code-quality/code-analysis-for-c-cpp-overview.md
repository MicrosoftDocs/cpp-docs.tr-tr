---
title: C/C++ için kod analizi genel bakış
ms.date: 04/28/2018
ms.topic: conceptual
helpviewer_keywords:
- annotations, code analysis
- build integration, code analysis
- C/C++ code analysis
- IDE, code analysis
- pragma directive, code analysis
- code analysis, C/C++
- code analysis tool
- command line, code analysis
- C++, code analysis
- check-in policies, code analysis
- '#pragma directives, code analysis'
- C, code analysis
ms.assetid: 81f0c9e8-f471-4de5-aac4-99db336a8809
ms.openlocfilehash: e5f5b75057985dc769c8f1ab84765d628dc42fcc
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040319"
---
# <a name="code-analysis-for-cc-overview"></a>C/C++ için kod analizi genel bakış

C/C++ Kod Analizi Aracı, C/C++ kaynak kodunuzda olası arızaların bilgilerini sağlar. Araç tarafından bildirilen yaygın kodlama hataları, arabellek taşmaları, Başlatılmamış bellek, null işaretçi başvurusu ve bellek ve kaynak sızıntılarını içerir. Araç, [C++ temel yönergeleri](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)karşı denetimleri de çalıştırabilir.

## <a name="ide-integrated-development-environment-integration"></a>IDE (tümleşik geliştirme ortamı) Tümleştirmesi

Kod Analizi Aracı, Visual Studio IDE içinde tamamen tümleşiktir.

Yapı işlemi sırasında, kaynak kodu için oluşturulan tüm uyarılar Hata Listesi görüntülenir. Uyarıya neden olan kaynak koda gidebilir ve sorunun nedeni ve olası çözümleriyle ilgili ek bilgileri görüntüleyebilirsiniz.

## <a name="command-line-support"></a>Komut satırı desteği

Aşağıdaki örnekte gösterildiği gibi, komut satırından çözümleme aracını da kullanabilirsiniz:

```cmd
C:\>cl /analyze Sample.cpp
```

**Visual Studio 2017 sürüm 15,7 ve üzeri:** Aracı, CMake dahil olmak üzere herhangi bir derleme sistemiyle komut satırından çalıştırabilirsiniz.

## <a name="pragma-support"></a>#pragma desteği

`#pragma`Uyarıları hata olarak değerlendirmek, uyarıları etkinleştirmek veya devre dışı bırakmak ve tek kod satırları için uyarıları gizlemek için yönergesini kullanabilirsiniz. Daha fazla bilgi için bkz. [pragma yönergeleri ve __pragma anahtar sözcüğü](/cpp/preprocessor/pragma-directives-and-the-pragma-keyword).

## <a name="annotation-support"></a>Ek açıklama desteği

Ek açıklamalar, kod analizinin doğruluğunu geliştirir. Ek açıklamalar, işlev parametreleri ve dönüş türlerinde ön ve son koşullar hakkında ek bilgiler sağlar. Daha fazla bilgi için bkz. [C/C++ kod hatalarını azaltmak IÇIN sal ek açıklamalarını kullanma](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md).

## <a name="run-analysis-tool-as-part-of-check-in-policy"></a>İade ilkesinin bir parçası olarak analiz aracını Çalıştır

Tüm kaynak kodu iadelerinin belirli ilkeleri karşıladıklarından emin olmak isteyebilirsiniz. Özellikle, çözümlemenin en son yerel yapıya bir adım olarak çalıştırılmış olduğundan emin olmak istersiniz. Kod Analizi iade ilkesini etkinleştirme hakkında daha fazla bilgi için bkz. [Kod Analizi Iade Ilkeleri oluşturma ve kullanma](/visualstudio/code-quality/how-to-create-or-update-standard-code-analysis-check-in-policies).

## <a name="team-build-integration"></a>Takım derlemesi tümleştirmesi

Azure DevOps derleme işleminin bir adımı olarak kod analizi aracını çalıştırmak için derleme sisteminin tümleşik özelliklerini kullanabilirsiniz. Daha fazla bilgi için bkz. [Azure Pipelines](/azure/devops/pipelines/index).

## <a name="see-also"></a>Ayrıca bkz.

- [Hızlı başlangıç: C/C++ için kod analizi](quick-start-code-analysis-for-c-cpp.md)
- [İzlenecek yol: hatalar için C/C++ kodunu analiz etme](walkthrough-analyzing-c-cpp-code-for-defects.md)
- [C/C++ İçin Kod Analizi Uyarıları](code-analysis-for-c-cpp-warnings.md)
- [C++ Temel Yönergeleri denetleyicilerini kullanma](using-the-cpp-core-guidelines-checkers.md)
- [C++ Temel Yönergeleri denetleyicisi başvurusu](code-analysis-for-cpp-corecheck.md)
- [Çalıştırılacak C++ kurallarını belirtmek için kural kümelerini kullanma](using-rule-sets-to-specify-the-cpp-rules-to-run.md)
- [Kod analizi araçlarını kullanarak sürücü kalitesini analiz etme](/windows-hardware/drivers/develop/analyzing-driver-quality-by-using-code-analysis-tools)
- [Sürücüler için kod analizi uyarıları](/windows-hardware/drivers/devtest/prefast-for-drivers-warnings)

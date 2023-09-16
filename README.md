<p align="center">
<img align="center" src="/static/img/polygon-logo.png" width="300">
</p>

<div align="Center">
<h1>0xPolygon Wiki</h1>
<h3>The Value Layer of the Internet</h3>

[![MIT license](https://img.shields.io/badge/License-MIT-blue.svg)](#LICENSE)
[![made-with-Markdown](https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg)](https://www.markdownguide.org/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](docs/general/contributing.md)
[![Contributors](https://img.shields.io/github/contributors-anon/0xPolygon/wiki)](https://github.com/0xPolygon/wiki/graphs/contributors)
[![Discord](https://img.shields.io/discord/714888181740339261?color=1C1CE1&label=Polygon%20%7C%20Discord%20%F0%9F%91%8B%20&style=flat-square)](https://discord.com/invite/XvpHAxZ)
[![Twitter](https://img.shields.io/twitter/follow/0xPolygon.svg?style=social)](https://twitter.com/0xPolygon)

</div>

<p align="left">
  The Polygon Wiki serves as the central source of truth for Polygon. Spearheaded by Polygon Labs, 
  it is a community-centric initiative that aims to provide the most current and comprehensive resources for 
  those interested in learning about, developing on, or maintaining projects within the Polygon ecosystem.
</p>

| ❗ Please note that the first half of this README provides an overview of Polygon, while the second half focuses on the repository and source. |
| ---------------------------------------------------------------------------------------------------------------------------------------------- |

<!-- TOC -->

- [Polygon Overview](#polygon-overview)
  * [What is Polygon?](#what-is-polygon-)
    + [Matic Network -> Polygon](#matic-network----polygon)
    + [Polygon 2.0](#polygon-20)
  * [Current Polygon Stack](#current-polygon-stack)
    + [PoS](#pos)
    + [zkEVM](#zkevm)
    + [Supernets](#supernets)
    + [Miden](#miden)
    + [ID](#id)
  * [Proposed Polygon 2.0 Stack](#proposed-polygon-20-stack)
    + [Architecture](#architecture)
      - [1. Staking Layer](#1-staking-layer)
      - [2. Interop Layer](#2-interop-layer)
      - [3. Execution Layer](#3-execution-layer)
      - [4. Proving Layer](#4-proving-layer)
      - [Modular Design](#modular-design)
      - [Future-Proof](#future-proof)
    + [Governance](#governance)
      - [Three Governance Pillars](#three-governance-pillars)
      - [Community Involvement](#community-involvement)
    + [Tokenomics](#tokenomics)
      - [Key Features of POL](#key-features-of-pol)
    + [Evolution of Polygon's Development Frameworks](#evolution-of-polygon-s-development-frameworks)
      - [Framework Comparison](#framework-comparison)
      - [Key Takeaways](#key-takeaways)
  * [Key Polygon Repositories](#key-polygon-repositories)
    + [Polygon 2.0 Repositories under 0xPolygon](#polygon-20-repositories-under-0xpolygon)
    + [zkEVM Repositories under 0xPolygonHermez](#zkevm-repositories-under-0xpolygonhermez)
    + [Polygon PoS Repositories under MaticNetwork](#polygon-pos-repositories-under-maticnetwork)
- [Repository Overview](#repository-overview)
  * [State of the Docs](#state-of-the-docs)
    + [What to Expect?](#what-to-expect-)
  * [Configuration Guide](#configuration-guide)
    + [Static-Site Generator](#static-site-generator)
    + [Deployments](#deployments)
    + [Algolia DocSearch](#algolia-docsearch)
    + [Google Analytics](#google-analytics)
    + [Translations](#translations)
    + [Files and Folders](#files-and-folders)
    + [Priority Labels (`P#`)](#priority-labels---p---)
  * [How to Contribute to the Polygon Wiki](#how-to-contribute-to-the-polygon-wiki)
    + [How to Contribute Changes via the Polygon Wiki Website](#how-to-contribute-changes-via-the-polygon-wiki-website)
    + [How to Locally Run the Polygon Wiki](#how-to-locally-run-the-polygon-wiki)
      - [Setup Steps](#setup-steps)
  * [Primary Maintainers](#primary-maintainers)
  * [License](#license)

<!--/ TOC -->

---

# Polygon Genel Bakış

Bu bölüm, Polygon'un evrimini ve çözüm yığınını kapsamlı bir şekilde tanıtmaktadır. Okuyuculara Polygon'un ne olduğu, stratejik odak alanları gibi Polygon 2.0 ve ekosistemini oluşturan çeşitli bileşenler hakkında net bir anlayış sunmayı amaçlar.

## Polygon Nedir?

Polygon, dijital değer değişimi için evrensel bir katman olarak işlev gören öncü bir blockchain protokolüdür.

### Matic Network -> Polygon

Başlangıçta Ethereum'u bir hibrid Plasma yan zinciri ile ölçeklemeyi amaçlayan Matic Network olarak piyasaya sürülen Polygon, dönüştürücü bir evrim geçirmiştir. Ethereum'un ölçeklenebilirliğini ve çok yönlülüğünü artırmak için tasarlanmış kapsamlı bir çözüm paketine dönüşmüştür. Bu stratejik dönüşüm, çeşitli kullanım durumlarının farklı ihtiyaçlarını ele almayı amaçlayan geniş kapsamlı araştırma ve testlerle desteklenmiştir. Ek olarak, sıfır bilgi teknolojisinin (zk-tech) ortaya çıkışı, blockchain teknolojisinin artık kitlesel benimseme için iyi donanımlı olduğunu gösteren önemli bir dönemeçtir.

Bu çeşitli çözümler bağımsız protokoller olarak var olmamaktadır; bunun yerine, birleşik bir Polygon protokolünün ayrılmaz bileşenleri olarak işlev görmektedirler. Polygon'un yaklaşan sürümü, bu bileşenleri daha da rafine etmeyi ve sorunsuz bir şekilde entegre etmeyi amaçlamaktadır.

### Polygon 2.0

Bu gelişmeler üzerine inşa edilerek, Polygon Labs "Polygon 2.0" adlı, internet için evrensel bir değer katmanı oluşturmayı amaçlayan özel bir protokol tanıtmıştır. Bununla, tümü sorunsuz likidite ile birleştirilmiş Layer 2 çözümlerinin bir ağını birbirine bağlar. Böylece, Polygon 2.0, blockchain teknolojisinin ne başarabileceğinin sınırlarını zorlamayı hedeflemektedir, içerdiği özellikler:

- **Evrensel Blockchain Erişimi**: Blockchain teknolojisine erişimi demokratikleştirir, kitlesel benimseme için yolu açar.
- **Ethereum Uyumu**: Hem ölçeklenebilirliği hem de işlevselliği artırmak için Ethereum'un yol haritasıyla yakından uyum sağlar.
- **Akıcı Likidite**: Çeşitli Katman 2 çözümlerini sorunsuz bir şekilde entegre eden tutarlı bir likidite ekosistemi oluşturur.
- **Etkileşimli Mesajlaşma ve Bileşenlik**: Çeşitli ürün paketleri ve blockchain tabanlı çözümler arasında sorunsuz iletişim ve etkileşim sağlar.
- **Adaptif Modülerlik**: Kolay özelleştirme ve gelecekteki yükseltmeler için esnek bir mimari sağlar.
- **Neredeyse Anlık İşlem Sonuçlanması**: Hızlı ve güvenilir işlem onayları garanti eder, genel kullanıcı deneyimini artırır.

## Güncel Polygon Yığınağı

Bugüne kadar, Polygon çeşitli uygulama ihtiyaçlarını karşılamak üzere tasarlanmış bir ürün ve çözüm yelpazesi sunmaktadır. Aşağıda, mevcut Polygon yığınının ana ürün paketleri yer almaktadır:

### PoS

Kanıta Dayalı Sahiplik (Proof-of-Stake, PoS) ağı, Polygon'un Katman 2 ölçekleme çözümlerinin omurgasını oluşturur. Merkezi olmayan uygulamalar ve işlemler için güvenli ve etkin bir platform sağlar.

### zkEVM

zkEVM, Polygon'un sıfır bilgi temelli Ethereum Sanal Makinesi'dir. Ethereum uyumlu blockhain'lere ölçeklenebilirlik ve gizlilik getirmeyi amaçlar.

### Supernets

Supernets, Polygon Edge konsensus istemcisi üzerinde PolyBFT konsensüsü ile çalışan uygulama özel zincirleridir. Merkezi olmayan uygulamalar için ölçeklenebilirlik ve etkileşimli çalışabilirlik sunarlar.

### Miden

Miden, tamamen EVM-uyumlu bir zk-rollup'tır. Sıfır bilgi kanıtlarının avantajları ile ölçeklenebilir ve güvenli bir Katman 2 çözümü sağlamayı amaçlar.

### ID

Polygon ID, blockchain üzerinde güvenli ve doğrulanabilir kimlik yönetimi sağlamayı amaçlayan merkezi olmayan bir kimlik çözümüdür.

Bu bileşenler topluca, her biri ekosistemin genel ölçeklenebilirliğine, güvenliğine ve etkileşimli çalışabilirliğine katkıda bulunurken belirli ihtiyaçları karşılar şekilde mevcut Polygon yığınını oluşturmaktadır.

## Önerilen Polygon 2.0 Yığınağı

### Mimari

Polygon 2.0, ölçeklenebilirlik, güvenlik ve etkileşimli çalışabilirlik için kapsamlı bir çözüm sağlamak üzere çok katmanlı bir mimari ile tasarlanmıştır. Mimari, dört ana katmandan oluşmaktadır:

#### 1. Staking Katmanı

Staking Katmanı, ağın omurgasını oluşturur ve güvenlik ile konsensus sağlar. Doğrulayıcı yönetimi ve staking operasyonlarından sorumludur, ağın genel bütünlüğünü sağlar.

#### 2. Etkileşimli Çalışabilirlik Katmanı

Interop Katmanı, farklı blockchain ağları arasında sorunsuz iletişimi mümkün kılmaya odaklanır. Çeşitli Katman 2 çözümleri ve hatta diğer Katman 1 blockchain'leri arasında varlık ve veri transferini kolaylaştırmak için LXLY köprüsünü kullanır.

#### 3. Yürütme Katmanı

Bu katman, tüm hesaplamaların gerçekleştiği yerdir. zkEVM, zk-Rollups gibi çeşitli yürütme ortamlarını destekler ve geliştiricilere uygulamaları için en uygun olanı seçme olanağı tanır.

#### 4. Kanıt Katmanı

Kanıt Katmanı, gerçekleştirilen işlemler için kriptografik kanıtlar oluşturmaktan sorumludur. Bu kanıtlar daha sonra işlemleri sonlandırmak için Staking Katmanı tarafından doğrulanır.

Birlikte, bu katmanlar ölçeklenebilir, güvenli ve etkileşimli bir ekosistem sunmak için uyum içinde çalışır, blockchain teknolojisinin başarabileceği sınırları zorlar.

#### Modüler Tasarım

Polygon 2.0'ın modüler yapısı, geliştiricilerin her katmandan farklı bileşenleri bir araya getirmesine olanak tanır, böylece belirli bir uygulama için özelleştirilmiş bir çözüm oluştururlar. Bu modülerlik, konsensus mekanizmaları, yürütme ortamları ve veri erişilebilirlik seçeneklerine de uzanır.

#### Geleceğe Dayanıklı

Polygon 2.0, ortaya çıktıkça yeni teknolojileri entegre etme yeteneği ile geleceğe dayanıklı olarak tasarlanmıştır. Bu, çerçevenin hızla gelişen blockchain manzarasının ön saflarında kalmasını sağlar.

Aşağıdaki diyagram, Polygon 2.0'ın çeşitli katmanlarını göstermektedir.

<p align="center">
<img align="center" src="/static/img/readme/polygon2.0-layers.png" width="900">
</p>

### Yönetişim

Polygon 2.0, topluluğa Polygon ağı üzerinde tam kontrol vermayı amaçlayan ileriye dönük bir merkezi olmayan yönetişim çerçevesi sunar. Bu yönetişim modeli, özellikle Ethereum'unki gibi kanıtlanmış blockchain yönetişim sistemlerinden ilham alır. Çerçeve, üç ana temel üzerine inşa edilmiştir: Protokol Yönetişimi, Sistem Akıllı Sözleşmeleri Yönetişimi ve Topluluk Hazinesi Yönetişimi.

#### Üç Yönetişim Temeli

1. **Protokol Yönetişimi**: Polygon İyileştirme Önerisi (PIP) çerçevesi, Polygon protokollerinin geliştirilmesi için açık bir platform olarak hizmet verir. Polygon 2.0'da, PIP çerçevesi tüm izinsiz yığına kapsam sağlayacak ve topluluğun yükseltmeleri önermesine ve araştırmasına olanak tanıyacaktır.

2. **Sistem Akıllı Sözleşmeleri Yönetişimi**: Bu temel, akıllı sözleşmeler olarak uygulanan protokol bileşenlerinin yükseltilebilirliğine odaklanır. Topluluk tarafından yönetilen bir Ekosistem Konseyi, bu yükseltmelerden sorumlu olacaktır. Konsey, güvenli ve ölçeklenebilir karar verme için özel olarak tasarlanmış bir yönetişim çerçevesi altında çalışacaktır.

3. **Topluluk Hazinesi Yönetişimi**: Kendini sürdürebilir bir Topluluk Hazinesi, kamu yararına olan projeleri finanse etmek ve umut verici ekosistem projelerini desteklemek için kurulacaktır. Bu hazine'nin yönetişimi, başlangıçtaki bir kuruldan daha açık topluluk tarafından yönlendirilen yönetişim mekanizmalarına evrilecektir.

<p align="center">
<img align="center" src="/static/img/readme/polygon2.0-governance-pillars.png" width="900">
</p>

#### Topluluk Katılımı

Topluluk geri bildirimleri ve katılımı, yönetişim sürecinin ayrılmaz bir parçasıdır. Doğrulayıcılar, kullanıcılar, altyapı sağlayıcılar ve dApp geliştiricilerinden geri bildirim almak için çeşitli kanallar, forum gönderileri ve topluluk çağrıları dahil, kullanılır.

### Tokenomik

Polygon'un yerel tokeni MATIC, 2020'deki kuruluşundan bu yana ağın büyümesinde kilit bir rol oynamıştır. Polygon 2.0'ın tanıtılmasıyla, MATIC'e teknik bir yükseltme olarak yeni bir token, **POL**, önerilmektedir. POL, sahiplerine çeşitli faydalar ve teşvikler sunacak şekilde tasarlanmış üçüncü nesil hiper üretken bir token olarak tasarlanmıştır.

#### POL'un Ana Özellikleri

- **Üçüncü Nesil Token**: POL, hiper üretken token kavramını tanıtır. İlk ve ikinci nesil tokenlerin aksine, POL sahiplerinin birden fazla zinciri doğrulamasına ve bu zincirler içinde birden fazla rol üstlenmesine olanak tanır, bu sayede pratiğe dökülebilir sınırsız fırsatlar sunar.

- **Büyük Faydalar**: POL, kullanıcılar ve geliştiriciler için sürtünme yaratmadan ekosistem güvenliği, sonsuz ölçeklenebilirlik ve topluluk sahipliği sağlamayı amaçlar.

- **Çok Yönlü Fayda ve Teşvikler**: Doğrulayıcılar, doğrulayıcı kümesine katılmak için POL yatırmak zorundadır. Bir kez yatırıldığında, herhangi bir Polygon zincirini doğrulayabilir ve protokol ödülleri, işlem ücretleri ve ekstra ödüller dahil olmak üzere birden fazla teşvik akışı oluşturabilirler.

- **Geleceğe Dayanıklı Ekosistem**: POL, bir Topluluk Hazinesini finanse etmek için sürekli bir emisyona sahip olacaktır, bu hazine Polygon topluluğu tarafından yönetilecektir. Bu hazine, protokol gelişimini, araştırmayı, ekosistem burslarını ve benimsenme teşviklerini destekleyecektir.

- **Problemsiz Yükseltme**: MATIC'ten POL'a geçiş, basit bir teknik işlemle kolaylaştırılacaktır. Token sahipleri MATIC'i bir yükseltme akıllı sözleşmesine gönderecek ve bu otomatik olarak eşdeğer miktarda POL döndürecektir.

### Polygon'un Geliştirme Çerçevelerinin Evrimi

Polygon'un egemen blok zincirleri inşa etmek için blok zinciri geliştirme çerçevesi zamanla önemli ölçüde evrim geçirmiştir, her iterasyon yeni özellikler ve yetenekler getirmiştir. Aşağıda, Polygon Edge, Supernets ve en son Zincir Geliştirme Kiti (CDK) arasındaki ana farkları ve özellikleri özetleyen bir karşılaştırma tablosu bulunmaktadır.

#### Çerçeve Karşılaştırması

| Özellik              |  Edge       | Supernets  | CDK                           |
|---------------------|-------------|------------|-------------------------------|
| **Katman**          | Katman 3    | Katman 3   | Katman 2                       |
| **Konsensus**       | IBFT        | PolyBFT    | zk-tabanlı / PolyBFT          |
| **Odak**            | Uygulama Zincirleri| Uygulama Zincirleri, Altyapı ve Özelleştirmeler | Uygulama Zincirleri, Altyapı, Özelleştirmeler, Modüler Geliştirme, Maliyet Azaltma |
| **Ölçeklenebilirlik**| Sınırlı    | Genişletilmiş Blok Alanı | Sınırsız                    |
| **Entegrasyon**     | Sınırlı     | Özel Yerel Köprü          | Evrensel Katmanlı Köprü     |
| **Yönetişim**       | Yok        | Özelleştirilebilir | Özelleştirilebilir           |
| **Veri Erişilebilirliği**| Zincir İçi| Zincir İçi | Özelleştirilebilir            |
| **Modülerlik**      | Sınırlı     | Sınırlı    | Evet                           |
| **Bileşenler**      | Edge istemcisi + Ethereum'da çekirdek sözleşmeler | Edge istemcisi + EVM-tabanlı kök zincir + egemen çekirdek sözleşmeler | Polygon 2.0'ın bir parçası olan özelleştirilebilir bileşenler |

#### Ana Çıkarımlar

- **Polygon Edge**: İlk olarak, Ethereum uyumlu blok zinciri ağları oluşturmak için uygulama zincirleri başlatmak amacıyla bir SDK olarak hizmet verdi, Katman 3 çözümleri olarak işlev gördü.

- **Polygon Supernets**: Edge'den evrim geçirerek uygulama zincirleri için altyapı geliştirme ve önyükleme karmaşıklıklarıyla başa çıkmayı amaçlar. Supernets, ayrıca gelişmiş entegrasyon ve özelleştirme seçenekleri sunar, aynı zamanda Katman 3 çözümleri olarak işlev görür.

- **Polygon CDK**: En yeni ve sofistike iterasyon olan CDK, Katman 2 çözümlerine odaklanır. Modülerliği ve özelleştirilebilirliği somutlaştırır, Polygon 2.0'dan keskin protokol ilkelini kullanır. Bu, geliştiricilerin benzersiz gereksinimlere uygun zincirler mimarlamalarını sağlar.

<p align="center">
<img align="center" src="/static/img/readme/polygon2.0-layers-1.png" width="900">
</p>

https://github.com/0xPolygon/wiki/assets/25497083/d848aecf-7f20-41d1-8382-80a41c622b25

## Ana Polygon Depoları

Polygon ekosistemini güçlendiren temel kod tabanlarını keşfedin. Bu bölüm, geliştiriciler, şirketler ve topluluk üyeleri için bir başlangıç noktası olarak en temel depolar için hızlı bağlantılar ve açıklamalar sunar.

### 0xPolygon Altında Polygon 2.0 Depoları

| Kategori                 | Depo Adı                                                         | Açıklama                                                                                       |
|--------------------------|------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| **Edge**                 | [Polygon Edge](https://github.com/0xPolygon/polygon-edge)         | Polygon'un kenar hizmetleri için bir depo.                                                     |
| **CDK**                  | [CDK Validium Node](https://github.com/0xPolygon/cdk-validium-node)| Validium düğümü dağıtımı için bir CDK.                                                         |
|                          | [CDK Veri Erişilebilirliği](https://github.com/0xPolygon/cdk-data-availability)| Veri erişilebilirlik çözümleri için bir CDK.                                                   |
|                          | [CDK Validium Sözleşmeler](https://github.com/0xPolygon/cdk-validium-contracts)| CDK Validium tarafından kullanılacak olan akıllı sözleşme uygulaması.                           |
| **Çekirdek**             | [Çekirdek Sözleşmeler](https://github.com/0xPolygon/core-contracts)| Polygon ağının çekirdeğini oluşturan akıllı sözleşmeler.                                       |
| **DApps ve Keşif**       | [DApp Keşif Polygon](https://github.com/0xPolygon/dapp-explorer-polygon)| Polygon ağı için bir DApp keşif platformu.                                                      |
| **Köprüler ve Entegrasyon** | [PoS ZkEVM Köprü](https://github.com/0xPolygon/pos-zkevm-bridge)| PoS ortamında ZkEVM için bir köprü.                                                             |
| **Araçlar**              | [Gaz Değiştirici](https://github.com/0xPolygon/gas-swapper)        | Gaz değişimi için bir araç.                                                                     |
|                          | [Indicia](https://github.com/0xPolygon/indicia)                   | Indicia, bir Polygon servisi için bir depo.                                                     |
| **ZkEVM**                | [ZkEVM Sarıcı](https://github.com/0xPolygon/zkevm-wrapper)         | ETH ve ERC20 tokenlerini ZkEVM'e transfer etmek için sarıcı sözleşmeler.                        |
| **Ekonomik Modeller**    | [Polygon 2.0 Ekonomik Model](https://github.com/0xPolygon/polygon2.0-economic-model)| Polygon 2.0'da doğrulayıcı teşvikleri ve ekosistem güvenliğini incelemek için bir simülasyon modeli.  |

### 0xPolygonHermez Altında zkEVM Depoları

| Kategori                  | Depo Adı                                                            | Açıklama                                                                                       |
|---------------------------|---------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| **Kanıtlayıcı (Prover)**  | [zkEVM Kanıtlayıcı](https://github.com/0xPolygonHermez/zkevm-prover)  | ZkEVM için kanıtlayıcı.                                                                         |
| **Düğüm (Node)**          | [zkEVM Düğüm](https://github.com/0xPolygonHermez/zkevm-node)         | ZkEVM için düğüm uygulaması.                                                                    |
| **Sözleşmeler**           | [zkEVM Sözleşmeler](https://github.com/0xPolygonHermez/zkevm-contracts)| ZkEVM için akıllı sözleşmeler.                                                                  |
| **Köprü Hizmeti**         | [zkEVM Köprü Hizmeti](https://github.com/0xPolygonHermez/zkevm-bridge-service)| ZkEVM için köprü hizmeti.                                                                       |
| **PIL Kütüphaneleri**     | [PIL2 Stark JS](https://github.com/0xPolygonHermez/pil2-stark-js)    | PIL2 STARK'lar için JavaScript kütüphanesi.                                                     |
|                           | [PILCOM](https://github.com/0xPolygonHermez/pilcom)                  | ZkEVM için PILCOM kütüphanesi.                                                                  |
| **Test Vektörleri**       | [zkEVM Test Vektörleri](https://github.com/0xPolygonHermez/zkevm-testvectors)| ZkEVM için test vektörleri.                                                                     |
| **Ortak Kütüphaneler**    | [zkEVM CommonJS](https://github.com/0xPolygonHermez/zkevm-commonjs)  | ZkEVM için CommonJS kütüphanesi.                                                                |
| **İletişim Protokolleri** | [zkEVM İletişim Protokolü](https://github.com/0xPolygonHermez/zkevm-comms-protocol)| ZkEVM için iletişim protokolü.                                                                  |
| **JavaScript Kanıtlayıcılar** | [zkEVM ProverJS](https://github.com/0xPolygonHermez/zkevm-proverjs) | ZkEVM için JavaScript kanıtlayıcı.                                                              |
| **Goldilocks**            | [Goldilocks](https://github.com/0xPolygonHermez/goldilocks)          | ZkEVM için Goldilocks kütüphanesi.                                                              |
| **PIL STARK**             | [PIL STARK](https://github.com/0xPolygonHermez/pil-stark)            | ZkEVM için PIL STARK kütüphanesi.                                                               |
| **ROM**                   | [zkEVM ROM](https://github.com/0xPolygonHermez/zkevm-rom)            | ZkEVM için Salt Okunur Bellek (Read-Only Memory).                                               |
| **ASM Derleyici**         | [zkASMCOM](https://github.com/0xPolygonHermez/zkasmcom)              | ZkEVM için ZkASM derleyici.                                                                     |
### MaticNetwork Altında Polygon PoS Depoları

| Kategori                  | Depo Adı                                                            | Açıklama                                                                                       |
|---------------------------|---------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| **Çekirdek Bileşenler**   | [Heimdall](https://github.com/maticnetwork/heimdall)                 | PoS Ağı için Heimdall katmanı.                                                                 |
|                           | [Bor](https://github.com/maticnetwork/bor)                           | PoS Ağı için Bor düğümü.                                                                       |
|                           | [Tendermint](https://github.com/maticnetwork/tendermint)             | PoS uyumlu konsensus motoru için Tendermint çatalı.                                             |
|                           | [Cosmos SDK](https://github.com/maticnetwork/cosmos-sdk)             | PoS Ağı için Cosmos SDK çatalı.                                                                 |
| **Token Yönetimi**        | [Polygon Token Listesi](https://github.com/maticnetwork/polygon-token-list)| PoS ağındaki tokenlerin listesi.                                                              |
|                           | [Polygon Token Varlıkları](https://github.com/maticnetwork/polygon-token-assets)| PoS ağı için token varlıkları.                                                                |
| **Altgraflar**           | [Altgraflar](https://github.com/maticnetwork/subgraphs)              | PoS Ağı için altgraflar.                                                                       |
| **CLI Araçları**          | [Matic CLI](https://github.com/maticnetwork/matic-cli)               | PoS Ağı için komut satırı arayüzü.                                                             |
|                           | [Polygon CLI](https://github.com/maticnetwork/polygon-cli)           | Polygon için komut satırı arayüzü.                                                             |
| **Gaz Yönetimi**          | [Matic Gaz İstasyonu](https://github.com/maticnetwork/maticgasstation)| PoS Ağı için gaz istasyonu.                                                                    |
| **Portallar ve Köprüler** | [PoS Portal](https://github.com/maticnetwork/pos-portal)             | PoS Ağı için Kanıt Temelli Sahiplik (Proof of Stake) portalı.                                  |
| **Teklifler**             | [Polygon İyileştirme Teklifleri](https://github.com/maticnetwork/Polygon-Improvement-Proposals)| Polygon İyileştirme Teklifleri için depo.                                                       |
| **SDK'lar ve Kütüphaneler**| [Matic.js](https://github.com/maticnetwork/matic.js)                 | PoS Ağı için JavaScript kütüphanesi.                                                            |
| **DevOps**                | [Düğüm Ansible](https://github.com/maticnetwork/node-ansible)         | Düğüm yönetimi için Ansible scriptleri.                                                         |
|                           | [Terraform Polygon Supernets](https://github.com/maticnetwork/terraform-polygon-supernets)| Polygon Supernets için Terraform scriptleri.                                                    |
| **Sözleşmeler**           | [Sözleşmeler](https://github.com/maticnetwork/contracts)             | PoS Ağı için akıllı sözleşmeler.                                                                |
|                           | [Başlangıç Sözleşmeleri](https://github.com/maticnetwork/genesis-contracts)| PoS Ağı için başlangıç sözleşmeleri.                                                            |
| **Kanıtlar ve API'ler**   | [Kanıt Oluşturma API](https://github.com/maticnetwork/proof-generation-api)| Kanıt oluşturma için API.                                                                       |
| **Erigon**                | [Erigon](https://github.com/maticnetwork/erigon)                     | Erigon Ethereum istemcisi.                                                                      |
| **Politikalar**           | [Polygon'da Politika](https://github.com/maticnetwork/Policy-at-Polygon)| Polygon'da politikalar.                                                                         |

---

# Depo Genel Bakış

Bu bölüm, bu depo'nun ayrıntılarına odaklanır, yapısını, içerdiği dosya ve klasör türlerini ve nasıl gezileceğini açıklar. Kaynak kodu, belgeler veya projeye katkıda bulunmak isteyen geliştiriciler ve katkıda bulunacaklar için bir rehber olarak hizmet vermektedir.

## Belgelerin Durumu

Polygon 2.0'ın devam eden gelişmeleriyle senkronize bir şekilde, Polygon belgeleme platformu da önemli iyileştirmeler için planlanmıştır. Başlangıçta bir "Geliştirici Merkezi" olarak tasarlanmış olan platform, çeşitli projelerin farklı ihtiyaçlarını etkili bir şekilde karşılamak için bir "Wiki"ye dönüşmüştür.

"Wiki" olarak adlandırılmış olsa da, platform geleneksel bir wiki'nin kapsamını aşar ve sadece bir bilgi deposu olmaktan daha fazlasını hizmet verir. Bu, farklı türlerde teknik içerik ve projenin farklı ihtiyaçlarını ve geliştirme aşamalarını karşılayabilecek çok yönlü bir platform olarak hizmet vermeyi amaçlar.

### Ne Beklemeli?

- **Bütünleşik Deneyim**: Ana Polygon web sitesi ile sorunsuz bir şekilde entegre olan belgeler, yeni, dinamik bir öğrenme deneyimi sunacak. Kaynak, sürekli bütünlük ve çok yönlülük için bağımsız varlığını sürdürecek.
- **Dinamik Belgelendirme**: Statik bir bilgi deposundan etkileşimli, dinamik bir bilgi platformuna geçiş.
- **Gelişmiş Öğrenme Deneyimi**: Başlangıç ​​seviyesindeyseniz veya bir uzman olursanız olun, öğrenmeyi kolaylaştırmak için sezgisel ve zenginleştirici içerik.
- **Kullanıcı Merkezli Tasarım**: Farklı kullanıcı kişiliklerini gözeterek tasarlanmış, geliştirici savunuculuğu ve ürün geliştirme ilkeleri tarafından yönlendirilen geliştirilmiş bilgi mimarisi ve gezinme.

Polygon topluluğu, kullanıcıların blockchain teknolojisinin keskin kenarında kalmalarına yardımcı olacak kapsamlı ve güncel bir kaynak sunmayı taahhüt etmektedir. Daha fazla güncelleme için bu alanı izleyin.

## Yapılandırma Rehberi

### Statik-Site Oluşturucu

[Polygon Wiki](https://wiki.polygon.technology/) [Docusaurus](https://docusaurus.io/) kullanılarak oluşturulmuştur, bu da statik dosyalarını hizmet etmeyi ve barındırmayı kolaylaştırır.

### Yayınlar

Polygon Wiki için yayın süreci iki ortamı içerir: **staging** ve **prod**. Her iki ortam da depo'nun `main` dalına karşı çalışacak şekilde yapılandırılmıştır.

Herhangi bir yayın—Staging veya Production olsun—depo'nun bir yöneticisinden açık yetkilendirme gerektirir.

- **Staging**: Bu ortam, test ve kalite güvencesi için kullanılır. Değişiklikler, Üretime taşınmadan önce burada ilk olarak konuşlandırılır.
- **Production**: Bu, son kullanıcılara erişilebilen canlı ortamdır. Staging ortamında başarılı doğrulamadan sonra Üretim'e taşınmalar yapılır.

### Algolia DocSearch

Belgeler, kullanıcılara güçlü ve kullanıcı dostu bir arama deneyimi sunmak için [Algolia'nın DocSearch](https://docsearch.algolia.com/) kullanmaktadır. DocSearch, belge web sitelerinde gezinmeyi kolaylaştırmak için özellikle tasarlanmıştır.

### Google Analytics

[Google Analytics](https://analytics.google.com/) platforma entegre edilmiştir ve kullanıcı etkileşimlerini izlemek ve değerli veriler toplamak için kullanılır. Bu, kullanıcı etkileşimini ve davranışını anlamak ve bu sayede belgelerin sürekli iyileştirilmesine yardımcı olur. Verilerin nasıl ele alındığı hakkında meraklı olanlar için, lütfen [Kullanım Şartlarımızı](https://polygon.technology/terms-of-use) inceleyin.

### Çeviriler

| ❗ Wiki, bir yeniden organizasyon ve güncelleme sürecindedir. Bu düzenleme tamamlandığında çeviri çalışmaları devam edecektir.       |
|----------------------------------------------------------------------------------------------------------------------------|

### Dosyalar ve Klasörler

Bu bölüm, Polygon Wiki deposundaki çeşitli dosya ve klasörlerin bir genel bakışını sağlar, her birinin amacını açıklar.

| İsim                  | Amaç                                                                                                           |
|-----------------------|-----------------------------------------------------------------------------------------------------------------|
| `.git`, `.github`     | Git yapılandırmalarını ve GitHub'a özgü ayarları yönetir.                                                       |
| `README.md`           | Polygon Wiki deposu için ana tanıtım dosyasıdır.                                                               |
| `sidebars.js`         | Yan çubuk navigasyonunu değiştirmek için kullanılır.                                                            |
| `docusaurus.config.js`| Web sitesi düzeni ve diğer Docusaurus ayarları için yapılandırma dosyasıdır.                                     |
| `src/pages/index.js`  | Blok yapısını ve altbilgi bağlantılarını değiştirmek için kullanılır.                                            |
| `yarn.lock`           | Tüm paket sürümlerini takip etmek için Yarn kilidi dosyasıdır.                                                  |
| `package.json`        | Projedeki bağımlılıkları ve komut dosyalarını belirtir.                                                         |
| `node_modules/`       | Tüm npm paketlerini ve bağımlılıkları içerir.                                                                   |
| `build/`              | Konuşlandırma için üretilen statik içeriği içerir.                                                              |
| `docs/`               | Wiki'nin içeriğini oluşturan Markdown dosyalarını içerir.                                                       |
| `static/`             | Görüntüler, CSS ve fontlar gibi statik varlıkları içerir.                                                       |
| `translations/`       | Farklı dilleri yönetmek için dosyaları içerir.                                                                  |

> Not: Bu, genel bir bakıştır ve gerçek depo, belirli işlevselliği için ek dosya ve klasörler içerebilir.

### Öncelik Etiketleri (`P#`)

GitHub etiketleri, sorunların aciliyetini ve önemini sınıflandırmak için kullanılır. Bu öncelik seviyeleri, aşağıdaki kriterlere dayanarak belgeleme ekibi tarafından belirlenir:

| Etiket | Etki Seviyesi                | Çözüm Zamanı | Örnek Kullanım Durumu                                            |
|--------|-----------------------------|-------------------------|------------------------------------------------------------------|
| P0     | Kritik ("Acil"): Hemen dikkat gerektirir | Aynı gün: Tüm diğer görevleri bırak ve hemen çöz | Web sitesi çöktü, işletme üzerinde ciddi etki oluşturuyor.       |
| P1     | Yüksek ("Önemli"): Önemli iş etkisi | 3 gün içinde: Hızlı bir şekilde ele alınmalı | Bir API uç noktası değişiyor, hemen belgelerin güncellenmesi gerekiyor. |
| P2     | Orta ("Yakında"): Zamanlanmış veya planlanmış | 2-3 hafta içinde: Yakın dönemde tamamlanabilir | Bir projenin API'sine yeni bir metodun yaklaşan eklemesi.        |
| P3     | Düşük ("Sahip Olunabilir"): Öneriler veya kavramsal güncellemeler | Belirlenmiş bir son tarihi yok: Mümkün olduğunda ele alın | Merkezi olmayanlığın geliştiriciler için avantajları hakkında önerilen bir blog yazısı. |

## Polygon Wiki'ye Nasıl Katkıda Bulunulur

Polygon Labs'taki Belgelendirme ekibi, Polygon Wiki'nin ana bakıcılarıdır ve
bu depoda oluşturulan tüm sorunlar ve çekme isteklerini inceleyeceklerdir. Eğer yazım hataları veya dilbilgisi hataları görüyorsanız,
lütfen düzeltmelerle bir çekme isteği gönderin. Daha büyük değişiklikler için, ilk olarak bir GitHub
sorunu ile bakıcılarla tartışmaya başlamak

| ❗ Note: The Polygon Wiki includes third-party content. Please review the [Third-Party Content Disclaimer](https://github.com/0xPolygon/wiki/blob/main/CONTENT_DISCLAIMER.md) for details. |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------- |

### Polygon Wiki Web Sitesi Üzerinden Değişiklik Katkısı Nasıl Yapılır

Polygon Wiki'ye katkıda bulunmak oldukça basittir. Başlamak için bir GitHub hesabınızın ve Markdown sözdiziminin temel bir anlayışının olması yeterlidir.

1. **Sayfayı Bulun**: Düzenlemek istediğiniz [Polygon Wiki sayfasını](https://wiki.polygon.technology/) ziyaret edin.
2. **Aşağıya İniniz**: Sayfanın en altına kaydırın.
3. **Düzenle Bağlantısı**: **Bu sayfayı düzenle** bağlantısına tıklayın. Bu sizi GitHub'da ilgili Markdown dosyasına yönlendirecektir.
4. **Düzenleme Modu**: GitHub'da olduğunuzda, düzenleme moduna girmek için sağ üst köşede yer alan kalem simgesine tıklayın.
5. **Düzenlemeler Yapın**: Gerekli değişiklikleri Markdown dosyasında yapın.
6. **Çekme İsteği Başlatın**: Aşağıya kaydırın ve **Çekme İsteği Oluştur**'a tıklayın.
7. **PR'nizin Başlığını Koyun**: Çekme isteğinize açıklayıcı bir başlık verin. Örneğin, "Başlangıç" sayfasını düzenliyorsanız, bunu *Update /docs/develop/getting-started.md* olarak adlandırabilirsiniz.
8. **Değişiklikleri Açıklayın**: Çekme isteği açıklamasında, değişikliklerinizin hangi sorunu çözdüğünü belirtin.  
   > Rehberlik için [GitHub Dokümantasyon: Bir Çekme İsteğini Bir Sorunla Bağlamak](https://docs.github.com/en/free-pro-team@latest/github/managing-your-work-on-github/linking-a-pull-request-to-an-issue#linking-a-pull-request-to-an-issue-using-a-keyword) sayfasına bakabilirsiniz.
9. **Ek Bilgi**: Yaptığınız değişikliklerin özlü bir özetini verin. Uygulamaysa ekran görüntüleri veya referanslar ekleyin.
10. **Gönder**: Değişiklik önerinizi sonlandırmak için **Değişiklikleri Öner**'e tıklayın. Bu, çatalınızda yeni bir dal oluşturacaktır.

Bir Polygon Wiki bakıcısı çekme isteğinizi gözden geçirecektir. Onaylanırsa, `main` dalına birleştirilecektir.

### Polygon Wiki'yi Yerelde Nasıl Çalıştırılır

> **Önkoşullar**:  
> - [Node.js](https://nodejs.org/en/download/) (sürüm >= 16.14.1)  
> - [Yarn](https://yarnpkg.com/getting-started/install) (sürüm >= 1.22)  
> **macOS Kullanıcıları İçin Not**: Xcode ve Komut Satırı Araçları gereklidir.

#### Kurulum Adımları

1. **Depoyu Çatallayın**
   > Rehberlik için [GitHub Dokümantasyon: Bir Depoyu Çatallamak](https://help.github.com/en/articles/fork-a-repo) sayfasına bakabilirsiniz.

2. **Çatalınızı Klonlayın**

   ```bash
   git clone git@github.com:[kullanıcı_adınız]/wiki.git
   ```

3. **Depoya Gitin**

    ```bash
    cd wiki
    ```

### Ana Depoyu Ekle

> [GitHub Dokümantasyon: Bir Çatal İçin Uzak Bir Depo Yapılandırmak](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/configuring-a-remote-for-a-fork) başlığına başvurun.

   ```bash
   git remote add upstream https://github.com/0xPolygon/wiki
   ```

### Çatalınızı Senkronize Edin

> [GitHub Dokümantasyon: Bir Çatalı Senkronize Etmek](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/syncing-a-fork) başlığına başvurun.

    ```bash
    git checkout master
    git fetch upstream
    git merge upstream/master
    ```

### Bağımlılıkları Yükleyin

   ```bash
   yarn install
   ```

   Site, Docusaurus kullanılarak oluşturulmuştur. Wiki'yi yerelde çalıştırmadan önce Docusaurus'u yüklemeniz gerekebilir.

   ```bash
   yarn add docusaurus
   ```

   Alternatif olarak, Docusaurus'u güncelleyebilirsiniz.

   ```bash
   yarn upgrade @docusaurus/core@latest @docusaurus/preset-classic@latest
   ```

### Wiki'yi Yerelde Çalıştırın

    ```bash
    yarn start
    ```

## Ana Bakıcılar

Aşağıda, Polygon Wiki'nin ana bakıcılarının bir listesi bulunmaktadır.

Eğer bu kişilerden biri tarafından iletişime geçilirse, iletişimin meşru olduğundan emin olmak için aşağıdaki adımları izleyin:

1. **İletişim Bilgilerini Doğrulayın**: İletişim detaylarını mesajın kökeni ile eşleştirin.
2. **İkinci Bir Kontrol Yapın**: İlk iletişimin meşruluğunu doğrulamak için bu listeye başka bir kişiye başvurun.

| ❗ Taklit Dolandırıcılıklarına Dikkat: Sizi iletişime geçen kişinin kimliğini her zaman çapraz doğrulayın. İletişim detaylarının mesaj kaynağı ile uyumlu olduğunu doğrulayın ve şüpheli durumlarda ek doğrulama yapın. |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------- |

- [@DannyS03](https://github.com/DannyS03): Ana iletişim, temel olarak CDK, PoS & ZK ve proje organizasyonu üzerine odaklanır.
- [@EmpieichO](https://github.com/EmpieichO): Temel olarak zkEVM & Miden ve spesifikasyonlar üzerine odaklanır.
- [@cerberushades](https://github.com/cerberushades): Temel olarak Polygon ID üzerine odaklanır.

## Lisans

Polygon Wiki, ücretsiz yazılım lisansı olan [MIT Lisansı](LICENSE) altında lisanslanmıştır.

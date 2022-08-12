# IDASH2022-任务 4：安全记录链接

**背景**：记录链接旨在链接来自两个或多个不同来源的记录，已在生物医学信息学中普遍采用，以链接不同医疗机构中同一患者的电子健康记录（EHR），例如，用于构建患者的纵向健康档案或对多个数据库中的个人记录进行重复数据删除等。出于对患者保密和/或机构数据共享政策的考虑，患者记录，尤其是身份密钥（例如，患者姓名、SSN、地址等），不能直接与对方共享。因此，需要一种安全算法来实现记录链接，而受保护的密钥仅以其加密形式共享。在安全记录链接的典型场景中，双方各自持有患者记录的私有数据集，并希望根据匹配的身份密钥（例如名字/姓氏、电子邮件、电话号码）识别两个数据集共享的患者、SSN、地址/邮政编码、出生日期、性别等）。值得注意的是，在实践中，记录链接并非微不足道，因为 1) 可能缺少键，而其他键在两个数据集中可能不准确，例如，地址可能会更改，名称可能包含拼写错误等； 2）一个数据集可能包含来自相同或非常相似（例如，来自同一家庭）患者的多条记录。在这里，任务是为两方实施安全记录链接算法，每方都持有患者记录的私有数据集，以使用多个可能非唯一的密钥来识别共享记录，而不与另一方共享每一方的数据集。纯文本。我们希望该算法可扩展到由数百万条记录组成的数据集，并且在计算中不涉及受信任的第三方。

**挑战**：我们挑战参赛团队实施安全的两方计算算法，该算法使用基于多个身份密钥的评分算法来识别匹配的记录。评分函数应设计为反映不同键的不同权重：一些键在没有缺失的情况下具有确定性权重（例如 SSN），而其他键（例如出生日期、电子邮件地址等）具有较低的权重取决于他们潜在的错误。每个key的错误率和缺失值的概率都会提前给出。该算法将输出按分数排序的匹配记录 (ID) 列表。参与团队可以考虑（但不是必须）使用 Meta 开发的 MPC 框架（https://github.com/facebookresearch/fbpcf）来实现他们的解决方案。
输入格式：每一方的患者记录数据库（一组键）。任一数据库中的每条记录都分配有一个唯一 ID，该 ID 只应在输出中使用。一些记录缺少数据。在一些非罕见的情况下，多条记录共享一些身份密钥（例如，相同的名字/姓氏、相同的地址）。
输出格式：双方得到一个秘密共享的 ID 列表，代表匹配的记录。

**安全要求**：两个半诚实的一方不应学习任何额外的信息，除非：
1.peer数据库中的记录数
2.匹配记录数
3.每个身份键的缺失值数量

**评估标准**：每个团队应提交一个解决方案。如果您计划提交使用截然不同的方法的多个解决方案，请联系组织者以获得批准。所有提交的解决方案都应满足安全要求；否则，提交将被取消资格。合格的解决方案将根据其准确性（即输出匹配记录的正确列表）进行排名。对于相同或非常接近（即差异在 0.1% 以内）的解，我们将评估算法的速度。有关数据的详细信息，请参阅常见问题解答。提交解决方案的指南稍后将在网站上提供。

**数据和代码骨架（8 月 11 日更新，密码：iDash2022）**：[链接]（https://indiana-my.sharepoint.com/:f:/g/personal/zhu11_iu_edu/EkFJ17EHX59LsO1Ekfc0TPkBi7CipeIHccd4wjb0CRhjzQ?e=qlt6aH )

常见问题解答：[链接](https://www.notion.so/huthvincent/All-you-need-to-know-in-the-Track-4-5f1948397ca246d197c9555a1663f80f)

输出要求：请在FAQ中查看

------------

# IDASH2022-Task 4: Secure Record Linkage
(organized by Haixu Tang and Xiaofeng Wang in collaboration with Ruiyu@Meta)

**Background**:  Record linkage, which aims to link the records from two or more distinct sources, has been commonly adopted in biomedical informatics to link electronic health records (EHRs) of the same patient in different medical institutions, e.g., for building the longitudinal health profile of the patient or for de-duplicating individual records in multiple databases, etc. Due to the concerns of patients’ confidentiality and/or the institutional data sharing policy, the patient records, in particular the identity keys (e.g, the patients’ name, SSN, address, etc), cannot be directly shared with the other party. Therefore, a secure algorithm is needed to achieve record linkage while the protected keys are only shared in their encrypted form. In a typical scenario of secure record linkage, two parties each hold a private data set of patients’ records, and wish to identify the patients shared by both data sets based on the matched identity keys (e.g. first/last name, email, phone number, SSN, address/zip code, birth date, gender, etc). Notably, in practice, the record linkage is non-trivial because 1) keys may be missing, while the others can be inaccurate in both datasets, e.g., the address may be changed, the name may contain typos etc; and 2) one dataset may contain multiple records from the same or very similar (e.g., from the same family) patients. Here, the task is to implement a secure record linkage algorithm for two parties, each holding a private dataset of patients’ records, to identify the shared records using multiple, possibly non-unique, keys without sharing each party’s dataset with the other party in plaintext. We expect the algorithm is scalable to the datasets consisting of millions of records, and does not involve a trusted third party in the computation.

**Challenge**:  We challenge the participating teams to implement a secure two-party computing algorithm that uses a scoring algorithm based on multiple identity keys to identify matched records. The scoring function should be designed to reflect the different weights of different keys: some keys have deterministic weights if they are not missing (e.g., SSN), while the other keys (e.g., birth dates, email address, etc) have lower weights to depending on their potential errors. The error rate and the probability of missing value for each key will be given in advance. The algorithm will output a list of matched records (IDs) ranked by the scores. The participating teams may consider (but not required) to use the MPC framework developed by Meta (https://github.com/facebookresearch/fbpcf) to implement their solutions.
Input format: A database of patient records (a set of keys) for each party. Each record in either database is assigned to a unique ID, which should only be used in the output. Some of the records have missing data. In some non-rare cases, multiple records share some identity keys (e.g. same first/last name, same address).
Output format: The two parties get a secret-shared list of IDs representing the matched records.

**Security requirement**:   The two semi-honest parties should learn no extra information except:
1.Number of records in peer’s database
2.Number of matched records
3.Number of missing values for each identity key

**Evaluation Criteria**:   Each team should submit a single solution. If you plan to submit multiple solutions that use substantially different approaches, please contact the organizers to get approval. All submitted solutions should fulfill the security requirement; otherwise, the submission will be disqualified. The qualified solutions will be ranked based on their accuracy (i.e., outputting the correct list of matched records). For the solutions with the same or very close (i.e., within 0.1% difference), we will evaluate the speed of the algorithm. For detail of the data, please see it in the FAQ. The guideline for submitting your solutions will be available at the website later.

**Data and Code Skeleto(Updated at Aug 11, password:iDash2022)**: [link](https://indiana-my.sharepoint.com/:f:/g/personal/zhu11_iu_edu/EkFJ17EHX59LsO1Ekfc0TPkBi7CipeIHccd4wjb0CRhjzQ?e=qlt6aH)

FAQ: [link](https://www.notion.so/huthvincent/All-you-need-to-know-in-the-Track-4-5f1948397ca246d197c9555a1663f80f)

Output requirement:   Please see it in the FAQ

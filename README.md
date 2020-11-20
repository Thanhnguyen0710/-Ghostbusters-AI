# -Ghostbusters-AI
Câu 1: Exact Inference Observation
Em sẽ duyệt hết danh sách các con ma nếu khoảng cách ước tính là none thì em cập nhật 
allPossible tại vị trí đó là 0 nếu khác none thì em sẽ tính khoảng cách chính xác và nếu  
emissionModel của khoảng cách đó lớn hơn không em sẽ cập nhật allPossible 
Sau khi duyệt hết mà khoảng cách ước lượng là node em sẽ cập nhật allPossible 

Câu 2: Exact Inference with Time Elapse
Em duyệt hết các vị trí hiện tại của ghost tìm các vị trí mới của con ghost có thể đi, duyệt
các vị trí đó lấy vị trí mới và prob rồi cập nhật vào allPossible
Sau đó gán self.beliefs = allPossible

Câu 3:Exact Inference Full Test
Em sẽ lập 1 mảng chứa các vị trí mà con ma đã tưng sống
Tạo 1 action map khởi tạo các giá trị là vô cùng
Duyệt các actionmap lấy ra vị trí mà pacman có thể đi tính từng khoảng cách của con pacman
đến các vị trí mà con ma đã tưng sống lấy số nhỏ nhất cập nhật vào actionmap
Đảo ngược các giá trị trong actionmap để trả về vị trí action lớn nhất

Câu 4:Approximate Inference Observation
Hàm initializeUniformly: Em sẽ append vị trí các con pacman vào trong particles
Hàm getBeliefDistribution: Em sẽ cập nhật các giá trị particles trong beliefs thêm 1
Hàm observe: 
Nếu khoảng cách ước lượng là none thì particles sẽ được gán là các mảng chứa các vị trí  
của ghost
Nếu không tạo 1 weightedParticles cập nhật emissionModel với tưng giá trị trong particles
Nếu số giá trị của weightedParticles  là 0 thì gọi laị hàm initializeUniformly không thì cập nhật
particles

Câu 5
Duyệt các vị trí của particles sau đó lấy vị trị mới và append vào newparticles 
Cập nhật self.particles = newParticles

Câu 6
Hàm initializeParticles: Lấy ra list của itertools sau đó cập nhật particles theo list đó
Hàm getBeliefDistribution: Em sẽ cập nhật các giá trị particles trong beliefs thêm 1
Hàm observeState:
Em sẽ kiểm tra xem số phần tử của mảng ước lượng mà nhỏ hơn số ghost thì thì return và không làm gì cả
Nếu không thì lấy emissionModels từ busters và noisyDistance
Duyệt lần lượt tất cả ghost và nếu giá trị ước lượng là none thì cập nhật particles
Sau đó duyệt particles với mỗi giá trị particles thì lại duyệt từng ghost nếu ghost không nằm trong getJailPosition thì cập nhật temweight và weightParticles
Sau đó nếu số các phần tử của weightParticles mà bằng 0 thì thực hiện hàm initialzeParticles, duyệt các ghost nếu noisyDistances là none thì cập nhật getParticleWithGhostInJail
Nếu không thì append vào newParticles và gán self.particles = newParticles
Câu 7
Duyệt các ghost lấy newPosDist từ getPositionDistributionForGhost và cập nhật vào newParticle
